<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Cuenta/>
  </div>
</template>

<script>
/*import HelloWorld from './components/HelloWorld.vue'*/
import Cuenta from './components/Cuenta'
export default {
  name: 'App',
  components: {
    /*HelloWorld,*/
    Cuenta
  }
}
</script>

<style>
/*#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
#app {
  text-align: center;
  min-height: 100vh;
  background: #031321;
  font-family: consolas;
}
</style>
