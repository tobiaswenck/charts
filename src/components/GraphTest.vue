<template>
    <v-container>
        <h1>ApexCharts</h1>
        <p>A simple Test of a few Apex Charts</p>
    </v-container>
    <v-container>
        <v-row>
            <div class="chart-one">
            <vue-apex-charts type="pie" :options="chartOptions" :series="series"></vue-apex-charts>
        </div>
        <div class="chart-two">
            <vue-apex-charts type="radialBar" :options="optionsTwo" :series="seriesTwo"></vue-apex-charts>
        </div>
        </v-row>
        
    </v-container>
</template>
<script setup>
import { ref } from 'vue';
import VueApexCharts from 'vue3-apexcharts';

// Define your chart options and series
const chartOptions = ref({
  chart: {
    type: 'pie',
  },
  labels: ['Team A', 'Team B', 'Team C', 'Team D'],
  responsive: [{
    breakpoint: 480,
    options: {
      chart: {
        width: 200
      },
      legend: {
        position: 'bottom'
      }
    }
  }]
});


var optionsTwo = {
chart: {
    height: 280,
    type: "radialBar",
  },

  series: [67],
  colors: ["#20E647"],
  plotOptions: {
    radialBar: {
      hollow: {
        margin: 0,
        size: "70%",
      },
      track: {
        dropShadow: {
          enabled: true,
          top: 2,
          left: 0,
          blur: 4,
          opacity: 0.15
        }
      },
      dataLabels: {
        name: {
          offsetY: -10,
          color: "#fff",
          fontSize: "13px"
        },
        value: {
          color: "#fff",
          fontSize: "30px",
          show: true
        }
      }
    }
  },
  fill: {
    type: "gradient",
    gradient: {
      shade: "dark",
      type: "vertical",
      gradientToColors: ["#87D4F9"],
      stops: [0, 100]
    }
  },
  stroke: {
    lineCap: "round"
  },
  labels: ["Progress"]
};



const series = ref([44, 55, 13, 43]);
const seriesTwo = ref([69]);
</script>
<style scoped>
    .chart-one {
        width: 50%;
        height: auto;
    }

    .chart-two {
        width: 50%;
        height: auto;
    }
</style>