<template>
  <div>
    <div id="chart">
        <apexchart type="donut" height="800px" :options="chartOptions" :series="series"></apexchart>
        <h1>Cydnie</h1>
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
        44, 55, 41, 17, 15
        ],
      chartOptions: {
        labels: ['one', 'two', 'three'],
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
      xaxis: {
        categories: ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
      },
      title: {
        text: 'Monthly Stock Pricing',
        align: 'center',
        style: {
          fontSize:  '20px',
        }
      },
        colors: ['#00897b', 'red', 'blue'],
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
  justify-content: center
}
</style>
