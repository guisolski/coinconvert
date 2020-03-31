<template>
  <div id="app">
    <h1>Coin Convert</h1>
    <div class="line">
      <Convert coinA="USD" coinB="BRL"/>
      <Convert coinA="BRL" coinB="USD"/>
    </div>
     <div class="line">
      <Convert coinA="EUR" coinB="BRL"/>
      <Convert coinA="BRL" coinB="EUR"/>
    </div>
  </div>
</template>

<script>
import Convert from "./components/Convert.vue";
export default {
  name: 'App',
  components: {
    Convert 
  }
}
</script>

<style>
#app {
  max-width: 900px;
  margin: auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-between;
}
</style>
