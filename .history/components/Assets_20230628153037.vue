<template>
  <div class="flex">
    <div class="text">
      <div>6个主模块</div>
      <div>22个子模块</div>
    </div>
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
            radius: "80%",
            center: ["50%", "50%"],
            data: [
              { value: 9, name: '资产管理', children: ['资产明细', '资产记录', '资产入库', '资产领用', '资产盘点', '资产调入', '资产调出', '资产注销', '资产出借'] },
              { value: 5, name: '经营性资产管理', children: ['部位管理', '经营性资产合同', '租金减免', '收租管理', '退租管理'] },
              { value: 3, name: '抄表管理', children: ['总表管理', '抄表-总表', '抄表-子表'] },
              { value: 3, name: '费用管理', children: ['杂费管理', '物业公司管理', '物业费管理'] },
              { value: 1, name: '租客管理', children: ['租客管理'] },
              { value: 2, name: '维修管理', children: ['维修申请', '维修费用报销'] },
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
              },
              
            textStyle: {
                fontFamily: '黑体',
                fontSize: 12,
              }
            },
            tooltip: {
              formatter: (params) => {
                if (params.data.children) {
                  const children = params.data.children.map(child => `<br>${child}`)
                  return children.join('').slice(4) // 只显示子菜单，不包含大图标的名称
                }
                return params.name
              },
              textStyle: {
                fontFamily: '黑体',
                fontSize: 12,
              }
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
      margin-bottom: 30px;
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
