<template>
  <div id="app">
    <RangeUI/>
    <Clock/>
    <ToolBar/>
  </div>
</template>

<script>
import RangeUI from './components/RangeUI.vue'
import Clock from './components/Clock.vue'
import ToolBar from './components/ToolBar.vue'

export default {
  name: 'App',
  components: {
    Clock,
    RangeUI,
    ToolBar,
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
  color: white;
  position:relatives;
  height: 100%;
}
</style>
