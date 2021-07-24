<template>
  <div class="card text-center mx-auto pt-4 chart-wrapper" style="width: 30rem; height: 20rem;">
    <div id="chart">
      <apexchart type="donut" height="600px"
      :options="chartOptions1" :series="series1">
      </apexchart>
    </div>
  </div>
</template>

<script>
import jsonFile from './data.json';
export default {
  name: 'HelloWorld',
  data: function() {
    return {
    json: jsonFile,
    series1: [],
    chartOptions1: {
      labels: ['female', 'male', 'undefined'],
      colors:['#9e0059', '#78BFFF', '#5c0799'],
      chart: {
      id: 'vuechart-example',
      type: 'donut',
    },
    },
    plotOptions1: {
      pie: {
        size: '100%',
      },
    },
    title: {
      text: 'Gender',
      align: 'center',
      style: {
        fontSize: '20px',
      }
    },
    }
  },
    methods:{
      getData(){
        const valuesArray1 = [];
        this.json.profiles[0].data.forEach(element => {

          valuesArray1.push(element.value) ;
        });
        this.series1 = valuesArray1;
      },
      init(){
      },
    },
    mounted: function() {
        this.init();
        this.getData();
      }
  }
</script>

<style scoped>
  div.chart-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
  }
</style>
