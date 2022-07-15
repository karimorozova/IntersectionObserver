<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <IntersectionObserver/>
</template>

<script>
import IntersectionObserver from './components/IntersectionObserver.vue'

export default {
  name: 'App',
  components: {
    IntersectionObserver
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
