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
        '7月-12月(2022)': {
          '添加行数': 17709,
          '删除行数': 5380,
          '总行数': 12329
        },
        '1月-7月(2023)': {
          '添加行数': 29879,
          '删除行数': 20936,
          '总行数': 8943
        }
      };
  
      // 转换数据为echarts可用的格式
      var xAxisData = Object.keys(data);
      var seriesData = Object.entries(data).map(([_, value]) => {
        return {
          name: '总行数',
          type: 'bar',
          data: [value['总行数']]
        };
      });
  
      // 初始化echarts实例
      var chart = echarts.init(document.getElementById('chart'));
  
      // 配置项
      var options = {
        tooltip: {
          trigger: 'axis'
        },
        xAxis: {
          type: 'category',
          data: xAxisData
        },
        yAxis: {
          type: 'value'
        },
        series: seriesData
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
  