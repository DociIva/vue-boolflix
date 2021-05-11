<template>
  <div id="app">
    <!--header-->
    <header> 
      <!--da mettere classe da portare nel header-->
      <Header  @searchEvent="aggSearchText" />
    </header >
      <main>
        <Products :movies="moviesList"/>
      </main>
        

    <!--content-->
    
     
      
    
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
   data(){
     return {
       moviesList: [],
       apiURL:'https://api.themoviedb.org/3/search/movie?api_key=8b24efa1369bc43a281706238658d0d1&query=fantozzi',

      }
    },
  
  methods: { 
    //aggionamento del searchText
    aggSearchText(text) {
        axios.get(this.apiURL, {
          params: {
            api_key: '8b24efa1369bc43a281706238658d0d1',
            query: text,
          }
        })
        .then(res => {
          this.moviesList = res.data.results;
          console.log(this.moviesList);
        })  
    }
  }
   
}
</script>

<style lang="scss">
@import '@/styles/general';


</style>
