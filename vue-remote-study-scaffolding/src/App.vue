<template>
  <div id="app">
    <StudyManager msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import StudyManager from './components/StudyManager.vue'

export default {
  name: 'App',
  components: {
    StudyManager
  }
}
</script>

<style>
html, body {
  margin: 0;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
