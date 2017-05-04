<template>
  <div class="frist" id="frist">
    <h1 v-text="title"></h1>
    <h1>{{ msg }}</h1>
    <input type="text" name="" v-model="newArray" v-on:keyup.enter="onEnter">
    <ul v-bind:class="addStyle">
      <li v-for="item in items" v-bind:class="{finished: item.isFinished}" v-on:click="changeStatus(item)" >
        {{item.title}} <span v-html=" item.mark "></span>
      </li>
    </ul>
  </div>
</template>
<!-- 1.语法格式需要注意，空格，标点符号需要符合eslint检查过关，否则程序报错 ;
    2.vue方法属性与冒号不能有空格与大括号必须有空格间隔; 等式表达式必须有空格但不能超出两个空格
    3.字符串必须用单引号， singlequote
    4.注释不能写在自定义字符串模板里，注释必须用此注释符里
-->
<script>

export default {
  data () {
    return {
      msg: '第一次使用vue操作！',
      title: 'frist user vuejs do demo',
      addStyle: 'ulstyle',
      items: [
        {
          title: 'javascript',
          mark: '从入门到入门到再入门',
          isFinished: true
        },
        {
          title: '面向对象',
          mark: '闭包，原型，继承',
          isFinished: false
        }
      ],
      newArray: ''
    }
  },
  methods: {
    changeStatus: function (item) {
      item.isFinished = !item.isFinished
      // console.log()
    },
    onEnter: function () {
      this.items.push({
        title: this.newArray,
        isFinished: false
      })
      console.log(this.newArray)
      this.newArray = ''
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
.ulstyle li{
  display: block;
  font-size: 16px;
  color: #666;
}
li {
  display: inline-block;
  margin: 0 10px;
}
li.finished{
    color:pink;
}
a {
  color: #42b983;
}
</style>
