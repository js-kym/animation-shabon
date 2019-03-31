<template>
  <div id="app">
    <Shabon/>
    <Shabon/>
    <Shabon/>
    <Shabon/>
  </div>
</template>

<script>
import Shabon from './components/Shabon'

export default {
  name: 'App',
  components: {
    Shabon
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
  background-color: #091933;
}
</style>
