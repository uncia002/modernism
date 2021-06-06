<template>
  <div id="app">
    <RangeUI/>
    <Clock/>
  </div>
</template>

<script>
import RangeUI from './components/RangeUI.vue'
import Clock from './components/Clock.vue'
export default {
  name: 'App',
  components: {
    Clock,
    RangeUI,
  }
}
</script>

<style>
body{
  background-color:black;
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  position:relatives;
}
</style>
