<template>
  <div id="app">
    <home/>
  </div>
</template>

<script>
import Home from '@/components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
  html, body {
    padding: 0;
    margin: 0;
    height: 100%;
  }
  #app {
    height: 100%;
  }
</style>