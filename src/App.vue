<template>

  <div>
    <img alt="Vue logo" src="./assets/logo.png">
  <Log_in msg="Welcome to Your StartApp App"/>
  </div>

</template>

<script>
// import Home from './components/Home.vue'
import Log_in from './components/Log_in.vue'

export default {
  name: 'App',
  components: {
    // Home,
    Log_in,
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
  margin-top: 60px;
}
</style>
