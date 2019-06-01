<template>
  <div id="app">

  <h1>Conversor de Moedas</h1>
  
  <div class="linha">
    <conversor moeda-a="BRL" moedaB="USD"/>
    <conversor moeda-a="USD" moedaB="BRL"/>
  </div>
  <div class="linha">
    <conversor moeda-a="BRL" moedaB="EUR"/>
    <conversor moeda-a="EUR" moedaB="BRL"/>
  </div>
  <div class="linha">
    <conversor moeda-a="BRL" moedaB="CAD"/>
    <conversor moeda-a="CAD" moedaB="BRL"/>
  </div>
</div>

  
</template>

<script>
import Conversor from "./components/Conversor.vue"
export default {
  name: 'app',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
}

.linha {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
</style>
