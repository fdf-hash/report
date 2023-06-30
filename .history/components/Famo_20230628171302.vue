<template>
    <div class="flex">
      <div class="chart-container">
        <div class="chart" ref="chart"></div>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import * as echarts from "echarts"
  
  export default {
    mounted() {
      this.renderChart()
    },
    methods: {
      renderChart() {
        const chart = echarts.init(this.$refs.chart)
  
        const options = {
          tooltip: {
            trigger: "item",
            formatter: "{b}: {c}",
          },
          series: [
            {
              type: "pie",
              radius: "70%",
              center: ["50%", "50%"],
              data: [
                {
                  value: 2,
                  name: "罚没款缴款通知单",
                  children: [
                    "罚缴分离",
                    "罚缴不分离"
                  ],
                },
                {
                  value: 2,
                  name: "罚没票据",
                  children: [
                    "代收罚没款票据",
                    "罚没款专用收据（电子）"
                  ],
                },
                {
                  value: 1,
                  name: "集中汇缴",
                  children: ["汇总缴款书"],
                }
              ],
              itemStyle: {
                emphasis: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: "rgba(0, 0, 0, 0.5)",
                },
  
                textStyle: {
                  fontFamily: "黑体",
                  fontSize: 12,
                },
              },
              tooltip: {
                padding: 6,
                formatter: (params) => {
                  if (params.data.children) {
                    const children = params.data.children.map(
                      (child) => `<br>${child}`
                    )
                    return children.join("").slice(4) // 只显示子菜单，不包含大图标的名称
                  }
                  return params.name
                },
                textStyle: {
                  fontFamily: "黑体",
                  fontSize: 12,
                },
              },
            },
          ],
        }
  
        chart.setOption(options)
      },
    },
  }
  </script>
  
  <style lang="scss" scoped>
  .flex {
    font-family: "黑体";
    display: flex;
    font-size: 14px;
    font-weight: 600;
    align-items: center;
    .text {
      width: 200px;
      div:nth-child(1) {
        margin-bottom: 20px;
      }
    }
  }
  .chart-container {
    width: 100%;
    height: 400px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .chart {
    width: 100%;
    height: 100%;
  }
  </style>
  