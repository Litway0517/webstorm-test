<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <useing_vue_map msg="Welcome to Your Vue.js App"/>
    <selectOnline msg="xx" />
    <a href="/views/selectOnline.vue">selectOnline</a>
  </div>
</template>

<script>
import useing_vue_map from './views/useing_vue_map.vue'
import selectOnline from "./views/selectOnline.vue";

export default {
  name: 'App',
  components: {
    useing_vue_map,
    selectOnline
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
