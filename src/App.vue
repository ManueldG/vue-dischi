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
    
    <Choose @changeP="genere" />
    
    <Folder :gen="gen"/>
    
    <HelloWorld msg=""/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Choose from './components/Choose.vue'
import Folder from './components/Folder.vue'

export default {
  name: 'App',
  data(){
    return{
      gen:"1",
    }
  },
  components: {
    HelloWorld,Folder,Choose
  },
  methods:{
    genere(testo){
    console.log("prova Emit",testo);
    this.gen=testo;
    }
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
  background: linear-gradient(90deg, black 30%, transparent 60%)
  ,linear-gradient(
    to right, #e6e94d90 0%, #e6e94d90 50%, #13bd2f90 50%, #13bd2f90 100%
  ),linear-gradient(    
    45deg, #e6e94d90 0%,#e6e94d90 50%, #13bd2f90 50%, #13bd2f90 100%
  );
  background-size:40px 45px;
  color: blue; 
  #LOGO{
    margin: 100px;
    width:50px;
  }
}
</style>