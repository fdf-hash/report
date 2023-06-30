<template>
  <div class="flex">
    <div>
      <div>资产管理分为</div>
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
            radius: "55%",
            center: ["50%", "50%"],
            data: [
              {value: 5, name: "经营性资产管理"},
              {value: 3, name: "抄表管理"},
              {value: 3, name: "费用管理"},
              {value: 1, name: "租客管理"},
              {value: 2, name: "维修管理"},
              {value: 1, name: "职员管理"},
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
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
  display: flex;
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
