<template>
  <div>
    <div id="chart" style="width: 500px; height: 400px"></div>
  </div>
</template>

<script>
import * as echarts from "echarts"

export default {
  mounted() {
    // 提供的数据

    var data = [
      ["时间", "添加行数", "删除行数", "总行数"],
      ["7月-12月(2022)", 17709, 5380, 12329],
      ["1月-7月(2023)", 29879, 20936, 8943],
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
      series: [
        { type: "bar", label: { show: true, position: "top" } },
        { type: "bar", label: { show: true, position: "top" } },
        { type: "bar", label: { show: true, position: "top" } },
      ],
    }

    // 渲染图表
    chart.setOption(options)
  },
}
</script>

<style>
#chart {
  width: 600px;
  height: 400px;
}
</style>
