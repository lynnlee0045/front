<template>
  <d2-container >
    <div id='mapChart' style="height: 400px; width: 80%;display:inline-block" >
    </div>
    <div id='static' style=" background-color: black; height: 400px; width: 20%;display:inline-block" >
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
            xAxis: {
                data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            yAxis: {},
            series: [{
                name: '销量',
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
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
  }
}
</style>
