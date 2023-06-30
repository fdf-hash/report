<template>
  <div>
    <div id="git" style="width: 500px; height: 400px; margin: 0 auto"></div>
  </div>
</template>

<script>
import * as echarts from "echarts"

export default {
  mounted() {
    setTimeout(() => {
      var data = [
        ["时间", "添加行数", "删除行数", "总行数", "提交次数"],
        ["7月-12月(2022)", 17709, 5380, 12329, 108],
        ["1月-7月(2023)", 29879, 20936, 8943, 446],
      ]

      // 初始化echarts实例
      var git = echarts.init(document.getElementById("git"))

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
          {type: "bar", label: {show: true, position: "top"}},
          {type: "bar", label: {show: true, position: "top"}},
          {type: "bar", label: {show: true, position: "top"}},
          {type: "bar", label: {show: true, position: "top"}},
        ],
      }

      // 渲染图表
      git.setOption(options)
    }, 500)
  },
}
</script>

<style>
#git {
  width: 600px;
  height: 400px;
}
</style>
