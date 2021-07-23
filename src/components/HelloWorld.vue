<template>
  <div>
    <div id="chart">
      <apexchart type="donut" height="300px"
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
    series: [
      44, 55, 41
      ],
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
        fontSize: '100px',
      }
    },
    }
  },
    methods:{
      init(){
      },
    },
    mounted: function() {
        this.init();
      }
  }
</script>

<style scoped>
  div.chart-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
