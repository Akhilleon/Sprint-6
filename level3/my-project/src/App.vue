<template>
  <body>
  <div id="app">
    <HomeItem></HomeItem>
  </div>
  </body>
</template>

<script>
import HomeItem from './components/Home.vue'

export default {
  name: 'App',
  components: {
    HomeItem
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
body{
  width: 100%;
  height: 100%;
  margin: 0;
}
</style>
