<template>
    <v-container>
        <h1>EDITH Suite</h1>
        <p>Test Environment</p>
    </v-container>
    <v-container>

        <v-row style="height: 22rem;">
          <v-col>
            <v-card fill-height>
              <v-card-title>Projektzeit</v-card-title>
              <v-card-subtitle>BBL Audit</v-card-subtitle>
              <v-row>
                <v-col>
                  <v-card-text>Lorem ipsum dolor sit amet, consetetur 
                  sadipscing elitr, sed diam nonumy eirmod tempor 
                  invidunt ut labore et dolore magna aliquyam erat, 
                  sed diam voluptua. At vero eos et accusam et justo 
                  duo dolores et ea rebum. Stet clita kasd gubergren, 
                  no sea takimata sanctus est Lorem ipsum dolor sit amet.
                </v-card-text>
              </v-col>
              <v-col>
                <VueApexCharts type="radialBar" :options="chartOptions" :series="series"></VueApexCharts>
              </v-col>
              </v-row>
              
              
              <v-divider></v-divider>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn>Mehr Anzeigen</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col>
            <!-- <v-card fill-height>
              <v-card-title>Stundenübersicht</v-card-title>
              <v-card-subtitle>Aktueller Monat</v-card-subtitle>
              <v-card-text>Lorem ipsum dolor sit amet, consetetur 
                sadipscing elitr, sed diam nonumy eirmod tempor 
                invidunt ut labore et dolore magna aliquyam erat, 
                sed diam voluptua. At vero eos et accusam et justo 
                duo dolores et ea rebum.
              </v-card-text>
              <v-divider></v-divider>
              <v-btn>Mehr Anzeigen</v-btn>
            </v-card> -->
          </v-col>
        </v-row>
    </v-container>
    
</template>
<script setup>
import { ref, onMounted } from 'vue';
import VueApexCharts from 'vue3-apexcharts';
import ApexCharts from 'apexcharts';

const posts = ref([]);

const fetchData = async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    posts.value = await response.json();
  } catch (error) {
    console.error('Error fetching posts:', error);
  }
};


const series = ref([44, 55, 67, 83])

const chartOptions = ref({
  chart: {
    type: 'radialBar',
  },
  plotOptions: {
    radialBar: {
      dataLabels: {
        name: {
          fontSize: '22px',
        },
        value: {
          fontSize: '16px',
        },
        total: {
          show: true,
          label: 'Total',
          formatter: function (w) {
            // By default this function returns the average of all series. The below is just an example to show the use of custom formatter function
            return 249
          }
        }
      }
    }
  },
  labels: ['Dataset 1', 'Dataset 2', 'Dataset 3', 'Dataset 4'],
})


var options2 = {
  chart: {
    height: 280,
    type: "radialBar",
  },
  plotOptions: {
    radialBar: {
      dataLabels: {
        total: {
          show: true,
          label: 'TOTAL'
        }
      }
    }
  },
  labels: ['TEAM A', 'TEAM B', 'TEAM C', 'TEAM D']
};



const seriesTwo = ref([69]);

onMounted(() => {
  fetchData();
  console.log(posts.value);
});
</script>
<style scoped>
    .chart-one {
        width: 25%;
        height: auto;
    }

    .chart-two {
        width: 25%;
        height: auto;
    }
</style>