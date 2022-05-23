<template>
  <div id="app">
    <Nav/>
  </div>
</template>

<script>
import Nav from './components/nav.vue'
export default {
  name: 'app',
  components: {
    Nav
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
