<template>
  <div class="hello">
    <div id="index">
      <h2>1. 参考文献</h2>
      <a href="https://jp.vuejs.org/v2/guide/index.html">はじめに — Vue.js</a>
      <p>ブラウザでdeveloper toolでVueの状態がみれる状態にしておく</p>
    </div>

    <div id="app1">
      <h2>2. 展開</h2>
      <h1>{{ message }}</h1>
      <p>展開: VueのMustache構文 二重波括弧</p>
    </div>

    <div id="app2">
      <h2>3. ディレクティブ v-bind</h2>
      <button :disabled="buttonFlag">ボタン</button>
      <p>v-bind - バインディング（Binding）</p>
    </div>

    <div id="app-3">
      <h2>4. 条件分岐 v-if</h2>
      <span v-if="seen">Now you see me</span>
    </div>

    <div id="app-4">
      <h2>5. list v-for :key</h2>
      <ol>
        <li v-for="todo in todos" :key="todo">
          {{ todo.text }}
        </li>
        <p>Elements in iteration expect to have 'v-bind:key' directives.</p>
      </ol>
    </div>

    <div id="app-5">
      <h2>6. ユーザ入力制御 v-on:</h2>
      <p>{{ message5 }}</p>
      <button v-on:click="reverseMessage">Reverse Message</button>
    </div>

    <div id="app-6">
      <h2>7. ユーザ入力制御 v-model:</h2>
      <p>{{ message6 }}</p>
      <input v-model="message6" />
    </div>

    <div id="app-7">
      <h2>8. コンポーネント間のデータ共有: 親->子</h2>
      <p>{{ parentData }}</p>
    </div>

    <div id="app-7">
      <h2>9. コンポーネント間のデータ共有: 子->親</h2>
      <button v-on:click="execEmit">execEmit!!</button>
    </div>
  </div>
</template>

<script>
import dayjs from "dayjs";
dayjs.locale("ja");

export default {
  /** name */
  name: "HelloWorld",

  /** props */
  props: {
    parentData: String,
  },

  /** data */
  data() {
    return {
      message: "Hello Vue2!",
      buttonFlag: true,
      seen: true,
      todos: [
        { text: "Learn JavaScript" },
        { text: "Learn Vue" },
        { text: "Build something awesome" },
      ],
      message5: "Hello Vue2",
      message6: "Hello Vue2",
      childData: "childDataString",
    };
  },

  /** methods */
  methods: {
    reverseMessage() {
      this.message5 = this.message5.split("").reverse().join("");
    },

    execEmit() {
      this.$emit("execEmit", "childData");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: flex;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
