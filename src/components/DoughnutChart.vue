<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";

const labels = [
  "Appartements",
  "Auberges",
  "Hotels",
];

const data = {
  labels: labels,
  datasets : [{
    label: 'client by month',
      backgroundColor: [
        'rgb(255, 99, 132)',
        'rgb(54, 162, 235)',
        'rgb(255, 205, 86)'
      ],
    data: [45, 60, 90]
  }]
}

const config = {
  type: 'doughnut',
  data: data,
  options: {
    animations: {}
  }
};


onMounted(()=> {
  const myChart = new Chart(
      document.getElementById('myChart'),
      config
  );
})
</script>

<template>
  <canvas  height="250" id="myChart"></canvas>
</template>

<style scoped>
#myChart{
  width: 100px;
}
</style>