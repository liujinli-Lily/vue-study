<template>
  <div id="app">
    <!-- <router-view></router-view> -->
    <frist></frist>
  </div>
</template>

<script>
import Frist from './components/Frist'
export default {
  name: 'app',
  components: {
    Frist
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
