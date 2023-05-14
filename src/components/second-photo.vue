<template>
  <div id="main1" style="height: 380px;width: 1200px"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "second-photo",
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
          text:'全国各级网络举报部门受理举报数量',
          x:'center',
          y:'top',
          padding:[20,80,0,0],
          textStyle:{
            fontSize:20,
            color:'black'
          }
        },
        /*legend:{
          //orient:'vertical',
          y:'bottom',
          x:'center',
          margin:[40,0,20,0],
          data:[{name:'APP',icon:'rect'},
            {name:'网址',icon:'rect'}]
        },*/
        xAxis: {
          data: ['2021年1-12月', '2022年1-12月'],
          splitLine:{
            show:false,
            //alignWithLabel: true,
            /*lineStyle:{
              type:'dotted',
              width:2
            }*/
          },
          axisTick:{
            show:true,
            inside:true
            /*alignWithLabel:true,
            length:1,
            lineStyle:{
              type:'dotted',
              color:'black',
              width:1,
              cap:'round'
            }*/
          },
        },
        yAxis: {
          name:'单位：万件',
          axisTick:{
            show:false,
          },
          axisLabel:{
            show:false
          },
          splitLine:{
            show:false,
          },
        },
        series: [
          {
            data: [{
              value:16622.4,
              itemStyle: {
                color: '#5b99d1',
                /*normal:{
                  label:{
                    show:true,
                    position:top
                  }
                }*/
              }
            }, {
              value:17214.7,
              itemStyle: {
                color: '#eb4649',

              }
            }],
            itemStyle: {
              normal: {
                label: {
                  show: true, //开启显示
                  position: 'top', //在上方显示
                  textStyle: {
                    //数值样式
                    color: 'black',
                    fontSize: 12,
                  },
                },
              },
            },
            type: 'bar',
            barWidth:'34%'
            /*symbol:'circle',
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
            }*/
          },
        ]
      };
      this.myChart.setOption(this.option)
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.chartDom = document.getElementById("main1");
      this.myChart = echarts.init(this.chartDom);
      this.initChart();
    });
  }
}
</script>

<style scoped>

</style>