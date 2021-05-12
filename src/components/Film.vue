<template>
   <div class="card">
      <div class="poster">
         <div v-if="info.backdrop_path == null"></div>
         <div v-else>
              <img :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" alt="copertina">
         </div>
      </div>
       <div class="details-film">
            <h2>{{info.title ? info.title : info.name }}</h2>
            <h3>{{info.original_title  ? info.original_title : info.original_name }}</h3>
            <span>{{info.overview}}</span>
       </div>
   </div>
</template>

<script>
export default {
   name: 'Film',
   props: {
      info: Object,
   },
   data() {
      return {
         // per la lingua
         flagsImg:[ 'it', 'en']
      }
   },
   methods: {
      flag(lingua) {
         // come fare per sapere se èe dentro l'array oppure no con includes| ritorna true o false
         return this.flagsImg.includes(lingua);
      }
   }
   
}
</script>

<style scoped lang="scss">
.card {
   position: relative;
   width: 100%;
   height: 100%;
}
img {
   width: 50px;
}

</style>