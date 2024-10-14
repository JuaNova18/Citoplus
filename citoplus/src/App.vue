<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <VisitorList msg="Welcome to Your Vue.js App"/>
</template>

<script>
import VisitorList from './components/VisitorList.vue';

export default {
  name: 'App',
  components: {
    VisitorList
  }
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
