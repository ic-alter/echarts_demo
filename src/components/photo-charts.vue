<template>
  <div id="main" style="height: 380px;width: 1200px"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "PhotoCharts",
  data(){
    return{
      chartDom: "",
      myChart: "",
      option: "",
    }
  },
  methods:{
    initChart(){
      this.option = {
        title:{
          show:true,
          text:'恶意拦截趋势',
          padding:[10,80,0,200],
          textStyle:{
            fontSize:20,
            color:'#546ca5'
          }
        },
        legend:{
          //orient:'vertical',
          y:'bottom',
          x:'center',
          margin:[40,0,20,0],
          data:[{name:'APP',icon:'rect'},
            {name:'网址',icon:'rect'}]
        },
        xAxis: {
          data: ['7月', '8月', '9月', '10月', '11月', '12月'],
          splitLine:{
            show:true,
            alignWithLabel: true,
            lineStyle:{
              type:'dotted',
              width:2
            }
          },
          axisTick:{
            show:true,
            alignWithLabel:true,
            length:1,
            lineStyle:{
              type:'dotted',
              color:'black',
              width:1,
              cap:'round'
            }
          },
        },
        yAxis: {
          name:'单位：万次',
          axisTick:{
            show:false,
          },
          axisLabel:{
            inside:true
          },
          splitLine:{
            show:false,
          },
        },
        series: [
          {
            name:'APP',
            data: [368000, 385000, 400000, 410000, 418000,413000],
            type: 'line',
            symbol:'circle',
            symbolSize:10,
            itemStyle:{
              normal:{
                color:'#80cdc5',
                borderColor:'#cdf5f1',
                borderWidth:3
              }
            },
            lineStyle:{
              normal:{
                color:'#80cdc5'
              }
            },
            areaStyle: {
              color: new echarts.graphic.LinearGradient(0,0,0,1,[{
                offset:0,
                color:'#84ded3'
              },{
                offset:1,
                color:'white'
              }])
            }
          },
          {
            name:'网址',
            data: [150000, 155000, 120000, 130000, 140000,149000],
            type: 'line',
            symbol:'circle',
            symbolSize:10,
            itemStyle:{
              normal:{
                color:'#8ea2d2',
                borderColor:'#dce5fb',
                borderWidth:3
              }
            },
            lineStyle:{
              normal:{
                color:'#8ea2d2'
              }
            },
            areaStyle: {
              color: new echarts.graphic.LinearGradient(0,0,0,1,[{
                offset:0,
                color:'#a9bceb'
              },{
                offset:1,
                color:'white'
              }])
            }
          }
        ]
      };
      this.myChart.setOption(this.option)
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.chartDom = document.getElementById("main");
      this.myChart = echarts.init(this.chartDom);
      this.initChart();
    });
  }
}
</script>

<style scoped>

</style>