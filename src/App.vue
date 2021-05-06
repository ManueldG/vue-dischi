<template>
  <div id="app">
    
    <HelloWorld msg="Prova"/>
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

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "~@fontsource/montserrat/400.css";
@import "~@fontsource/montserrat/600.css";


#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  
}
</style>
