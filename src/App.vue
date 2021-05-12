<template>
  <div id="app">
      <!--header-->
      <!--da mettere classe da portare nel header-->
      <Header @search="getRaccoltaDati"/>
    
      
     <!--content-->
      <Products/>  
    
  </div>
</template>

<script>
//import axios from "axios";
// IMPORTAZIONE DEI COMPONENTI
import Header from '@/components/Header.vue';
import Products from '@/components/Products.vue';

export default {
  name: 'App',
  components: {
    Header,
    Products,
  },
  methods: {
    // è un dato passato dal dal search su / 
    //con le connes hai preso il dato che viene registrato e l'evento al click
    getRaccoltaDati(searchText) {
      console.log(searchText);
    }
  }
}
</script>

<style lang="scss">
@import '@/styles/general';


</style>
