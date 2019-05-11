<template>
  <div id="app">
    <img alt="Vue logo" class="logo" src="./assets/logo.png">
    <Curso msg="Qual curso?"/>
  </div>
</template>

<script>
import Curso from './components/Curso.vue'

export default {
  name: 'app',
  components: {
    Curso
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
  /* margin-top: 60px; */
}
.logo{
  width: 200px;
}
body{
  background: #FFEB3B;
}
</style>
