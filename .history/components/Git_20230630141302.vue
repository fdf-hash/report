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
        dimensions: ['时间', '添加行数', '删除行数', '总行数'],
        source: [
          ['7月-12月(2022)', 17709, 5380, 12329],
          ['1月-7月(2023)', 29879, 20936, 8943]
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
          trigger: 'axis',
          axisPointer: {
            type: 'shadow'
          }
        },
        xAxis: {
          type: 'category',
          axisLabel: {
            rotate: -45
          }
        },
        yAxis: {},
        series: [
          {
            type: 'bar',
            encode: { x: '时间', y: '总行数' },
            emphasis: {
              focus: 'series'
            },
            itemStyle: {
              opacity: 1
            }
          }
        ]
      };
  
      // 渲染图表
      chart.setOption(options);
  
      // 监听鼠标悬停事件
      chart.on('mouseover', function(params) {
        var currentIndex = params.dataIndex;
        var series = chart.getOption().series[0];
  
        // 隐藏其他柱子
        series.itemStyle.opacity = function(dataIndex) {
          return dataIndex === currentIndex ? 1 : 0.3;
        };
  
        // 更新图表
        chart.setOption({ series: [series] });
      });
  
      // 监听鼠标移出事件
      chart.on('mouseout', function() {
        var series = chart.getOption().series[0];
  
        // 显示所有柱子
        series.itemStyle.opacity = 1;
  
        // 更新图表
        chart.setOption({ series: [series] });
      });
    }
  };
  </script>
  
  <style>
  #chart {
    width: 600px;
    height: 400px;
  }
  </style>
  