<template>
  <div class="chart_card">
    <!-- START:: TITLE -->
    <h4 class="chart_title mt-0">
      <slot name="chart_title"></slot>
    </h4>
    <!-- END:: TITLE -->

    <!-- START:: CHART -->
    <apexchart
      type="bar"
      height="380px"
      :options="barChartOptions"
      :series="barChartSeries"
    ></apexchart>
    <!-- END:: CHART -->
  </div>
</template>

<script>
export default {
  name: "BarCart",

  props: ["ChartLabels", "ChartData"],

  data() {
    return {
      // START:: BAR CHART DATA
      barChartOptions: {
        chart: {
          width: "100%",
          stacked: false,
        },
        dataLabels: {
          enabled: false,
        },
        plotOptions: {
          bar: {
            columnWidth: "55%",
            borderRadius: 5,
            horizontal: true,
          },
        },

        colors: ["#32E8E2", "#29479A", "#249AD5", "#FE8B90", "#6365F8"],

        labels: this.ChartLabels,

        xaxis: {
          labels: {
            show: true,
            style: {
              colors: "#78909c",
            },
          },
          axisBorder: {
            show: false,
          },
          axisTicks: {
            show: true,
          },
        },

        yaxis: {
          axisBorder: {
            show: true,
          },
          axisTicks: {
            show: false,
          },
          labels: {
            style: {
              colors: "#78909c",
            },
          },
        },
      },

      barChartSeries: this.ChartData,
      // END:: BAR CHART DATA
    };
  },
};
</script>
