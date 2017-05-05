<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ msgfromfather }}</h2>
    <button v-on:click="onClickbtn">click!!!!</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Son said to his father'
    }
  },
  props: ['msgfromfather'],
  methods: {
    onClickbtn: function () {
      this.$emit('child-tell-message', this.msg)
      console.log(this.msgfromfather)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
