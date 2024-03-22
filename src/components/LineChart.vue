<script setup>
import Chart from 'chart.js/auto';
import {onMounted, reactive, watchEffect} from "vue";

let months = []
let bookings = []

console.log(bookings)
console.log(months)

const data = {
  labels: months,
  datasets : [{
    label: 'Bookings by month',
    backgroundColor: 'rgb(255,255,255)',
    borderColor: 'rgb(206,53,53)',
    data: bookings
  }]
}

const config = {
  type: 'line',
  data: data,
  options: {
    animations: {}
  }
};


onMounted(()=> {
   const lineChart = new Chart(
      document.getElementById('lineChart'),
      config
  );

  fetch("data.json")
      .then((response)=> {
        return response.json()
      })
      .then((data)=> {
        data.forEach((element)=> {
          months.push(element.months)
          bookings.push(element.bookings)
        })
      })
  //GRAPHIQUE A AFFICHER AVEC LES VALEURS
})
</script>

<template>
  <canvas width="400" id="lineChart"></canvas>
</template>

<style scoped>

</style>