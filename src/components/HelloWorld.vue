<template>
  <div id="chart">
    <div class="card text-center mx-auto mb-3 pt-4 chart-wrapper" style="width: 30rem; height: 20rem;">
      <apexchart type="donut" height="600px"
      :options="chartOptions1" :series="series1">
      </apexchart>
    </div>

    <div class="card text-center mx-auto mb-3 pt-4 chart-wrapper" style="width: 30rem; height: 20rem;">
      <apexchart type="donut" height="600px"
      :options="chartOptions2" :series="series2">
      </apexchart>
    </div>

    <div class="card text-center mx-auto mb-3 pt-4 chart-wrapper" style="width: 30rem; height: 20rem;">
      <apexchart type="donut" height="600px"
      :options="chartOptions3" :series="series3">
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
    },
    title1: {
      text: 'Gender',
      },
    series2: [],
    chartOptions2: {
      labels: ['Below 25', 'Between 25 and 40', 'Above 40'],
      colors:['#9e0059', '#78BFFF', '#5c0799'],
    },
    title2: {
      text: 'Gender',
      },
    series3: [],
    chartOptions3: {
      labels: ['Costa Rica', 'India', 'Canada'],
      colors:['#9e0059', '#78BFFF', '#5c0799'],
    },
    title3: {
      text: 'Gender',
      }
    }
  },
    methods:{
      getData(){
        // Chart 1
        const valuesArray1 = [];
        this.json.profiles[0].data.forEach(element => {

          valuesArray1.push(element.value) ;
        });
        this.series1 = valuesArray1;
        // Chart 2
        const valuesArray2 = [];
        this.json.profiles[1].data.forEach(element => {

          valuesArray2.push(element.value) ;
        });
        this.series2 = valuesArray2;
        // Chart3
        const valuesArray3 = [];
        this.json.profiles[2].data.forEach(element => {

          valuesArray3.push(element.value) ;
        });
        this.series3 = valuesArray3;
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
