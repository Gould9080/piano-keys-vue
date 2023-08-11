<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <MainDiv msg="Eat a bean, eat a brog" />
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import MainDiv from './components/MainDiv.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    MainDiv
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html {
  background-color: rgb(250, 240, 229);
}

body {
  margin: 0;
}
</style>
