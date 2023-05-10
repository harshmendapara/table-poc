<template>
  <div id="app">
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  padding: 10px;
}
body {
  /* font-family: Arial, Helvetica, sans-serif !important; */
  font-family: 'Segoe UI';
}
</style>
