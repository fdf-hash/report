<template>
    <div>
      <div id="chart" style="width: 600px; height: 400px;"></div>
    </div>
  </template>
  
  <script>
  import * as echarts from 'echarts';
  
  export default {
    mounted() {
      // 提供的数据
      var data = {
        dimensions: ['时间', '指标', '数值'],
        source: [
          ['7月-12月(2022)', '添加行数', 17709],
          ['7月-12月(2022)', '删除行数', 5380],
          ['7月-12月(2022)', '总行数', 12329],
          ['1月-7月(2023)', '添加行数', 29879],
          ['1月-7月(2023)', '删除行数', 20936],
          ['1月-7月(2023)', '总行数', 8943]
        ]
      };
  
      // 初始化echarts实例
      var chart = echarts.init(document.getElementById('chart'));
  
      // 配置项
      var options = {
        dataset: {
          source: data.source
        },
        tooltip: {
          trigger: 'axis'
        },
        xAxis: {
          type: 'category',
          axisLabel: {
            rotate: -45
          }
        },
        yAxis: {},
        series: [
          { type: 'bar', encode: { x: '时间', y: '数值' } }
        ],
        color: ['#6EC88A', '#FF7373', '#FFAE57'] // 设置柱子的颜色
      };
  
      // 渲染图表
      chart.setOption(options);
    }
  };
  </script>
  
  <style>
  #chart {
    width: 600px;
    height: 400px;
  }
  </style>
  