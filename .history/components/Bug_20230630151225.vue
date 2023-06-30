<template>
    <div>
      <div id="bug" style="width: 500px; height: 400px;margin: 0 auto;"></div>
    </div>
  </template>
  
  <script>
  import * as ebugs from "ebugs"
  
  export default {
    mounted() {
      var data = [
        ["时间", "BUG问题数量"],
        ["2023", 100],
        ["2022", 0],
      ]
  
      // 初始化ebugs实例
      var bug = ebugs.init(document.getElementById("bug"))
  
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
  