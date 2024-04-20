<script>
import BarChart from "./components/BarChart.vue";
import DoughnutChart from "./components/DoughnutChart.vue";
import LineChart from "./components/LineChart.vue";


export default {
  name: 'App',
  components: { LineChart }
}
</script>

<template>
  <h1>KPI BOOKYES</h1>
  <div class="container">
    <div class="topDiv">
      <div class="topLeftDiv">
        <div class="datas">
          <div class="data">
            <h2>CLIENTS</h2>
            <p class="nombre">672 432</p>
          </div>
          <hr>
          <div class="data">
            <h2>CHIFFRE D'AFFAIRE</h2>
            <p class="nombre">3 455 873 $</p>
          </div>
          <hr>
          <div class="data">
            <h2>VISITES</h2>
            <p class="nombre">10 732 137</p>
          </div>
        </div>
        <table>
          <tr>
            <th>Type</th>
            <th>Quantité</th>
            <th>Conversion (%)</th>
            <th>CA (%)</th>
            <th>Durée moyenne location</th>
          </tr>
          <tr>
            <td>HOTELS</td>
            <td>364 431</td>
            <td>65 %</td>
            <td>50 %</td>
            <td>2 jours</td>
          </tr>
          <tr>
            <td>APPARTEMENTS / MAISONS</td>
            <td>234 290</td>
            <td>56 %</td>
            <td>38 %</td>
            <td>5 jours</td>
          </tr>
          <tr>
            <td>AUBERGES</td>
            <td>98 342</td>
            <td>54 %</td>
            <td>12 %</td>
            <td>3 jours</td>
          </tr>
        </table>
      </div>
      <div class="topRightDiv">
        <div class="doughnutChart">
          <h2>Clients by month</h2>
          <DoughnutChart/>
        </div>
        <div class="chiffresEtablissements">
          <div class="etablissements">
            <h3>Nouveaux établissements</h3>
            <button style="margin-left: 9px;">MOIS ▼</button>
          </div>
          <p class="nombre">34 567</p>
        </div>
      </div>
    </div>
    <div class="bottomDiv">
      <div class="lineChart">
        <LineChart/>
      </div>
      <div class="barChart">
        <BarChart/>
      </div>
    </div>
  </div>
</template>

<style scoped>
h1{
  display: flex;
  justify-content: center;
}
.container{
  margin-left: 5%;
  margin-right: 5%;
  width:90%;
}



.topDiv{
  display: flex;
  justify-content: space-between;
  height: 50vh;
}

.topLeftDiv{
  width: 70%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
.datas{
  display: flex;
  justify-content: space-around;
}
hr{
  margin: 0;
}
.data{
  display: flex;
  flex-direction: column;
  align-items: center;
}
table{
  border-spacing: 0;
}
td, th{
  border: 1px solid #b9b9b9;
  text-align: left;
  padding: 8px;
}
th{
  background-color: #dddddd;
}


.topRightDiv{
  width: 18%;
}
.doughnutChart{
  display: flex;
  flex-direction: column;
  align-items: center;
}
.doughnutChart>h2{
  margin: 0;
}
.chiffresEtablissements{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  margin-top: 30px;
  border: 1px solid black;
  padding: 8px;
}
h3{
  margin: 2px;
}
.etablissements{
  display: flex;
}


.bottomDiv{
  display: flex;
  justify-content: space-between;
  height: 35vh;
}

.lineChart{
  width: 45%;
}
.barChart{
  width: 45%;
}






.nombre{
  font-size: xxx-large;
  margin: 0;
}
</style>
