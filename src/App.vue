<template>
  <div id="app">
    <!-- <router-view></router-view> -->
    <frist></frist>
    <h3>child talking: {{childwords}}</h3>
    <component-a msgfromfather = "user props property" v-on:child-tell-message="ListenLhildMessage"></component-a>
  </div>
</template>
<!--
字符串模板名称需要转换成class-class模式
-->
<script>
import Frist from './components/Frist'
import ComponentA from './components/ComponentA'
export default {
  name: 'app',
  components: {
    Frist, ComponentA
  },
  data () {
    return {
      childwords: ''
    }
  },
  methods: {
    ListenLhildMessage: function (msg) {
      this.childwords = msg
    }
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
