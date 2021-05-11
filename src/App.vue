<template>
  <div id="app">
    <!--header-->
    <header> 
      <!--da mettere classe da portare nel header-->
      <Header />
    </header>
    

    <!--content-->
    <main>
     
        <div class="movies" v-for="film in moviesList" :key="film.id">
           <Products :movies="film" />
        </div>
        
       
      
    </main>
    
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
       apiURL:'https://api.themoviedb.org/3/search/movie?api_key=8b24efa1369bc43a281706238658d0d1&query=fantozzi',
       moviesList: [],
      }
   },
  created() {
    this.getFilm();
  },
  methods: { 
    getFilm() {
      axios.get(this.apiURL)
      .then(res=> {
        this.moviesList =res.data.results;
        console.log(res.data.results);
      })
    }

  }
}
</script>

<style lang="scss">
@import '@/styles/general';


</style>
