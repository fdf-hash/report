<template>
  <div>
    <div id="chart" style="width: 500px; height: 400px; margin: 0 auto"></div>
  </div>
</template>

<script>
import * as echarts from "echarts"

export default {
  mounted() {
    this.load()
  },
  mounted: {
    load() {
      var data = [
        ["时间", "BUG数量"],
        ["2023", 100],
        ["2022", 0],
      ]

      // 初始化echarts实例
      var chart = echarts.init(document.getElementById("chart"))

      // 配置项
      var options = {
        legend: {},
        tooltip: {},
        dataset: {
          source: data,
        },
        xAxis: {type: "category"},
        yAxis: {},
        series: [{type: "bar", label: {show: true, position: "top"}}],
      }

      // 渲染图表
      chart.setOption(options)
    },
  },
}
</script>

<style>
#chart {
  width: 600px;
  height: 400px;
}
</style>
