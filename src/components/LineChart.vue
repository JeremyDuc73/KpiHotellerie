<script>
import Chart from 'chart.js/auto';
import {Line} from "vue-chartjs";

export default {
  name: "LineChart",
  components: {Line},
  data: () => ({
    loaded: false,
    chartData: null
  }),
  async mounted() {
    this.loaded = false

    try {
      const {monthList} = await fetch("months.json")
      console.log(monthList)
      this.chartData.labels = monthList

      this.loaded = true
    } catch (e) {
      console.error(e)
    }
  }
}


</script>

<template>
  <div class="container">
    <Line v-if="loaded" :data="chartData" />
  </div>
</template>

<style scoped>

</style>