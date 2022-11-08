<template>
  <div id="app">
    <HelloWorld parentData="parentDataString" @execEmit="getExecEmit" />
    <div>
      <h3>受け取ったデータを親から見る</h3>
      <p>{{ childData }}</p>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },

  data() {
    return {
      childData: "",
    };
  },

  methods: {
    getExecEmit(getChildData) {
      this.childData = getChildData;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
