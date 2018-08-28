<template>
  <d2-container >
    <div id="wrapper">
      <div id='mapChart' style="height: 400px; width: 80%;display:inline-block" ></div>
      <div id='static' style=" background-color: black; height: 500px; width: 20%;display:inline-block" >
    </div>
    </div>
  </d2-container>
</template>

<script>
export default {
  data() {
    return {
      greeting: "Hello"
    }
  },
    mounted(){
    this.$nextTick(function() { 
      this.drawLine() 
    }) 
  },
  methods: {
    drawLine(){
        // 基于准备好的dom，初始化echarts实例
        let myChart = this.$echarts.init(document.getElementById('mapChart'))
        // 绘制图表
        myChart.setOption({
            title: { text: '在Vue中使用echarts' },
            tooltip: {},
            // xAxis: {
            //     data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            // },
            // yAxis: {},
            itemStyle: {
              // 阴影的大小
              shadowBlur: 100,
              // 阴影水平方向上的偏移
              shadowOffsetX: 0,
              // 阴影垂直方向上的偏移
              shadowOffsetY: 0,
              // 阴影颜色
              shadowColor: 'rgba(0, 0, 0, 0.5)'
            },
            series: [{
                name: '销量',
                type: 'pie',
                radius: '55%',
                data: [
                  {value:235, name:'视频广告'},
                  {value:274, name:'联盟广告'},
                  {value:310, name:'邮件营销'},
                  {value:335, name:'直接访问'},
                  {value:400, name:'搜索引擎'}
                ]
            }]
        });
    }
  }
}
</script>


<style lang="scss" scoped>
@import '~@/assets/style/public.scss';
.index-btn-group {
  color: $color-text-placehoder;
  span {
    color: $color-text-sub;
    &:hover {
      color: $color-text-main;
    }
  };
}
.wrapper {
  height: 500px;
}
</style>
