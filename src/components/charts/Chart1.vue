<style lang="scss" scoped>
  #chart1{
    width: 50%;
    height: 500px;

  }
</style>
<template>
  <div>
    <h2>{{msg}}</h2>
    <div id="chart1"></div>
  </div>
</template>
<script>
import echarts from 'echarts'
export default {
  data () {
    return {
      msg: 'chart1我是一个饼图吧'
    }
  },
  mounted () {
    let myChart = echarts.init(document.getElementById('chart1'))
    let option = {
      title: {
        text: '某站点用户访问来源',
        subtext: '纯属虚构',
        x: 'center'
      },
      tooltip: {
        trigger: 'item',
        formatter: '{a} <br/>{b} : {c} ({d}%)'
      },
      legend: {
        orient: 'vertical',
        left: 'left',
        data: ['直接访问', '邮件营销', '联盟广告', '视频广告', '搜索引擎']
      },
      series: [
        {
          name: '访问来源',
          type: 'pie',
          radius: '55%',
          center: ['50%', '60%'],
          data: [
            { value: 335, name: '直接访问' },
            { value: 310, name: '邮件营销' },
            { value: 234, name: '联盟广告' },
            { value: 135, name: '视频广告' },
            { value: 1548, name: '搜索引擎' }
          ],
          itemStyle: {
            emphasis: {
              shadowBlur: 10,
              shadowOffsetX: 0,
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            }
          }
        }
      ]
    }
    myChart.setOption(option)
    window.addEventListener('resize', function () {
      myChart.resize()
    })
  }

}
</script>
