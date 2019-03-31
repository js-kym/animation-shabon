<template>
  <div id="app">
    <Shabon :color="'#ff0000'"/>
    <Shabon :color="'#00ff00'"/>
    <Shabon :color="'#0000ff'"/>
    <Shabon :color="'#ff0000'"/>
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
