<script setup>
import Chart from 'chart.js/auto';
import {onMounted} from "vue";

const labels = [
  "Hotels",
  "Appartements",
  "Auberges"
];

const data = {
  labels: labels,
  datasets : [
      {
    label: '% Conversion',
    backgroundColor: 'rgb(32,65,121)',
    borderColor: 'rgb(206,53,53)',
    data: [34, 46, 21]
      },
    {
      label: '% CA',
      backgroundColor: 'rgb(149,11,11)',
      borderColor: 'rgb(206,53,53)',
      data: [52, 36, 12]
    }
      ]
}

const config = {
  type: 'bar',
  data: data,
  options: {
    animations: {}
  }
};


onMounted(()=> {
  const barChart = new Chart(
      document.getElementById('barChart'),
      config
  );
})
</script>

<template>
  <canvas width="400" id="barChart"></canvas>
</template>

<style scoped>
</style>