<template>
    <div>
        <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
            <!-- Card stats -->
            <div class="row">
                <div class="col-xl-3 col-lg-6">
                  <router-link to="/appointments" class="nav-link">
                    <stats-card title="Appuntamenti"
                                type="gradient-red"
                                sub-title="12 da schedulare"
                                icon="ni ni-calendar-grid-58"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 3.48%</span>
                            <span class="text-nowrap">Rispetto al mese scorso</span>
                        </template>
                    </stats-card>
                  </router-link>
                </div>
                <div class="col-xl-3 col-lg-6">
                  <router-link to="/customers" class="nav-link">
                    <stats-card title="Clienti"
                                type="gradient-orange"
                                sub-title="183"
                                icon="ni ni-single-02"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 12.18%</span>
                            <span class="text-nowrap">dal mese scorso</span>
                        </template>
                    </stats-card>
                  </router-link>
                </div>
                <div class="col-xl-3 col-lg-6">
                  <router-link to="/archive" class="nav-link">
                    <stats-card title="Files condivisi"
                                type="gradient-green"
                                sub-title="873"
                                icon="ni ni-cloud-upload-96"
                                class="mb-4 mb-xl-0"
                    >
                    </stats-card>
                  </router-link>
                </div>
                <div class="col-xl-3 col-lg-6">
                  <router-link to="/" class="nav-link">
                    <stats-card title="Altri indici?"
                                type="gradient-info"
                                sub-title="49,65%"
                                icon="ni ni-chart-bar-32"
                                class="mb-4 mb-xl-0"
                    >

                        <template slot="footer">
                            <span class="text-success mr-2"><i class="fa fa-arrow-up"></i> 54.8%</span>
                            <span class="text-nowrap">Since last month</span>
                        </template>
                    </stats-card>
                  </router-link>
                </div>
            </div>
        </base-header>
    </div>
</template>
<script>
  // Charts
  import * as chartConfigs from '@/components/Charts/config';
  // import LineChart from '@/components/Charts/LineChart';
  // import BarChart from '@/components/Charts/BarChart';

  // Tables
  // import SocialTrafficTable from './Dashboard/SocialTrafficTable';
  // import PageVisitsTable from './Dashboard/PageVisitsTable';

  export default {
    // components: {
    //   LineChart,
    //   BarChart,
    //   PageVisitsTable,
    //   SocialTrafficTable,
    // },
    data() {
      return {
        bigLineChart: {
          allData: [
            [0, 20, 10, 30, 15, 40, 20, 60, 60],
            [0, 20, 5, 25, 10, 30, 15, 40, 40]
          ],
          activeIndex: 0,
          chartData: {
            datasets: [],
            labels: [],
          },
          extraOptions: chartConfigs.blueChartOptions,
        },
        redBarChart: {
          chartData: {
            labels: ['Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
            datasets: [{
              label: 'Sales',
              data: [25, 20, 30, 22, 17, 29]
            }]
          }
        }
      };
    },
    methods: {
      initBigChart(index) {
        let chartData = {
          datasets: [
            {
              label: 'Performance',
              data: this.bigLineChart.allData[index]
            }
          ],
          labels: ['May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
        };
        this.bigLineChart.chartData = chartData;
        this.bigLineChart.activeIndex = index;
      }
    },
    mounted() {
      this.initBigChart(0);
    }
  };
</script>
<style></style>
