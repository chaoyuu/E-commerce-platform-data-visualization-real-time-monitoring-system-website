<!-- 商家分布图表 -->
<template>
  <div class='com-container' >
    地区销售排行图表
    <div class='com-chart' ref='rank_ref'></div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      chartInstance: null,
      allData: null,
  
    }
  },
  mounted () {
    this.initChart()
    this.getData()
    window.addEventListener('resize', this.screenAdapter)
    this.screenAdapter()
  },
  destroyed () {
    window.removeEventListener('resize', this.screenAdapter)
  },
  methods: {
    async initChart () {
   
       this.chartInstance = this.$echarts.init(this.$refs.rank_ref);
       const initOption = {};
       this.chartInstance.setOption(initOption);
   
    },
    async getData () {
     
      this.updateChart()
    },
    updateChart () {
      
       const dataOption ={};
      this.chartInstance.setOption(dataOption)
    },
    screenAdapter () {
    
      const adapterOption = {  }
      this.chartInstance.setOption(adapterOption)
      this.chartInstance.resize()
    },
   
  }
}
</script>

<style lang='less' scoped>
</style>
