<template>
  <div class="card text-center mx-auto pt-4 chart-wrapper" style="width: 30rem; height: 20rem;">
    <div id="chart">
      <apexchart type="donut" height="600px"
      :options="chartOptions" :series="series">
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
    series: [],
    chartOptions: {
      labels: ['female', 'male', 'undefined'],
      chart: {
      id: 'vuechart-example',
      type: 'donut',
    },
    },
    plotOptions: {
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
      myJson(){
        this.series =  this.json.profiles[0].data.forEach(element => {

          element.value ;
        });
      },
      init(){
      },
    },
    mounted: function() {
        this.init();
        console.log("from methods:", this.myJson());
        // console.log("this.json.profiles[0].data", this.json.profiles[0].data[0].value);
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
