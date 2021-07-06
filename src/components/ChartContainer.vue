<template>
  <div class="chart-container">
    <BarChart :height="365" :options="options" :chartData="chartData"/>
  </div>
</template>

<script>
import BarChart from '@/components/BarChart.vue'

export default {
  components: { BarChart },
  data: () => ({
    options: {
      responsive: true,
      maintainAspectRatio: false,
      legend: {
        onClick: (e) => e.stopPropagation(),
        display: true,
        position: 'bottom',
        labels: {
          boxWidth: 12,
          fontSize: 12,
          fontColor: '#222',
          filter: function(item) {
              return !item.text.includes('line');
          }
        },
        hover: {
          animationDuration: 0,
          mode: 'index',
          intersect: false,
        },
      },
      scales: {
        yAxes: [{
          stacked: true,
          ticks: {
            callback: function(label) {
                return label/1000+'k';
            }
          }
        }],
        xAxes: [ {
          stacked: true,
          categoryPercentage: 0.5,
          barPercentage: 1,
          gridLines: {
            display: false,
            drawBorder: false,
          }
        }]
      },
    },
    chartData: {
      datasets: [
        {
          type: 'line',
          label: 'line',
          data: [57050, 46025, 51035, 51040, 47035, 51040],
          borderColor: ['#FFE854'], 
          fill: false,
          strokeColor: 'none',
          pointRadius: 3,
          pointBorderColor: '#FFE854',
          pointBackgroundColor: '#FFE854',
          backgroundColor: '#FFE854',
        },
        {
          type: 'bar',
          label: 'Nett',
          data: [21000, 18000, 20000, 15000, 20000, 16000],
          backgroundColor: '#37B04C',
        },
        {
          type: 'bar',
          label: 'Gross',
          data: [19000, 17000, 19000, 20000, 15000, 20000],
          backgroundColor: '#289E45',
        },
        {
          type: 'bar',
          label: 'Average Purchase Value',
          data: [17000, 11000, 12000, 16000, 12000, 15000],
          backgroundColor: '#7AE28C',
        },
        {
          type: 'bar',
          label: 'Unit per Transaction',
          data: [50, 25, 35, 40, 35, 40],
          backgroundColor: '#707070',
        }, 
      ],
      labels: ['January', 'February', 'March', 'April', 'May', 'June']
    }
  })
}
</script>

<style>
  .chart-container  {
    width: 100%;
    height: auto;
  }
</style>