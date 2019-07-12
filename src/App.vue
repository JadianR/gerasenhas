<template>
  <div id="app">
    <Gerasenhas />
  </div>
</template>

<script>
import Gerasenhas from './components/Gerasenhas.vue'

export default {
  name: 'app',
  components: {
    Gerasenhas
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
