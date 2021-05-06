/*
Esercizio di oggi: Vue Dischi Musicali
nome repo: vue-dischi
Descrizione:
Attraverso una chiamata ajax all’API di boolean:
https://flynn.boolean.careers/exercises/api/array/music
avremo a disposizione una decina di dischi musicali.
Utilizzando Vue e i suoi componenti, stampiamo a schermo una card per ogni album.
Verificate i dati ritornati dall'API con Postman prima di inziare a scrivere codice, così da poter analizzare quanti e quali dati avete a disposizione.
Questo vi agevolerà poi anche nella scrittura del codice.
Link download Postaman: https://www.postman.com/downloads/
Vi ricordo che questo è un lavoro che si articolerà su due giornate.

 */

<template>
  <div id="app">
    <img src="@/../../logo.png" alt="Logo" id="LOGO">

    <Folder/>
    
    <HelloWorld msg=""/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Folder from './components/Folder.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,Folder
  }
}
</script>

<style scoped lang="scss">

@import "~bootstrap/scss/bootstrap";
@import "~@fontsource/montserrat/400.css";
@import "~@fontsource/montserrat/600.css";

#app {
  font-family: Montserrat,Helvetica, Arial, sans-serif;
  font-weight: 600;
  background-color: yellow;
  color: blue; 
  #LOGO{
    margin: 100px;
    width:50px;
  }
}
</style>