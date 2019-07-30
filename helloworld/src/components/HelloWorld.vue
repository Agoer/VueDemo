<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ msg1 }}</h2>
    <span v-bind:title="message">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
    <p v-if="seen">
      if else：现在你看到我了
    </p>
    <h1>下面是：for 循环</h1>
    <ol>
      <li v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ol>
    <p>{{ actionTitle }}</p>
    <button v-on:click="reverseMessage">反转消息</button>
    <p>{{ inputMessage }}</p>
    <input v-model="inputMessage" />

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '信息展示1',
      msg1:'信息展示2',
      message: '页面加载于 ' + new Date().toLocaleString(),
      seen:true,
      todos: [
      { text: '学习 JavaScript' },
      { text: '学习 Vue' },
      { text: '整个牛项目' }
    ],
      actionTitle:'hello button action',
      inputMessage: 'hello input',

    }
  },
  methods: {
    reverseMessage: function () {
      this.actionTitle = this.actionTitle.split('').reverse().join('')
    },
  },
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
