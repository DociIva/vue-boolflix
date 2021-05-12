<template>
  <div id="app">
      <!--header-->
      <!--da mettere classe da portare nel header-->
      <Header @search="getRaccoltaDati"/>
    
      
     <!--content    per portare da qua al componente-->
      <Products :filmList="filmList" :series="serieList"/>  
    
  </div>
</template>

<script>
import axios from "axios";
// IMPORTAZIONE DEI COMPONENTI
import Header from '@/components/Header.vue';
import Products from '@/components/Products.vue';

export default {
  name: 'App',
  components: {
    Header,
    Products,
  },
  data() {
    return {
       //chiamata unica di per la parte iniziale messa in una raccolta
       apiURL: 'https://api.themoviedb.org/3/search/' ,
       // Key api
       apiKey: '8b24efa1369bc43a281706238658d0d1',
       //raccolta
       filmList: [],
       serieList: [],
    }
  },
  methods: {
    // è un dato passato dal dal search su / 
    //con le connes hai preso il dato che viene registrato e l'evento al click
    getRaccoltaDati(searchText) {
      console.log(searchText);

      // controllo della chiamata| searchText non è vuoto

      if(searchText !== '') {
          //punto centralizzato
        const apiParametri = {
               api_key: this.apiKey,
                // paramentro 
                query: searchText,
                language:'it-IT',
        };
        /**
         *  X I FILM
         * chiamata API qua | concatenmento della scelta movie o serie tv | più dinamico
         */
        
        axios.get(this.apiURL + 'movie', {

              params: apiParametri,
    
         }). then(res => {
          this.filmList = res.data.results;
         });
        
         /**
         * X LE SEARIES 
         */
        axios.get(this.apiURL + 'tv', {
               // avr data
               params: apiParametri,
            
         }). then(res => {
          this.serieList = res.data.results;
         });
    
        }
    }
  }
}
</script>

<style lang="scss">
@import '@/styles/general';


</style>
