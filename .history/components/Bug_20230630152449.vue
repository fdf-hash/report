<template>
    <div>
      <div id="bug" style="width: 500px; height: 400px;margin: 0 auto;"></div>
    </div>
  </template>
  
  <script>
  import * as echarts from "echarts"
  
  export default {
    mounted() {
      var data = [
        ["BUG数量","文档问题"],
        [100,46]
      ]
  
      // 初始化echarts实例
      var bug = echarts.init(document.getElementById("bug"))
  
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
        ],
      }
  
      // 渲染图表
      bug.setOption(options)
    },
  }
  </script>
  
  <style>
  #bug {
    width: 600px;
    height: 400px;
  }
  </style>
  