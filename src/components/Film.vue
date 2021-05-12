<template>
   <div class="film">
       <ul>
   
          <li><img :src="`https://image.tmdb.org/t/p/w154/${info.poster_path}`" alt="copertina"> </li>
          <li>{{info.title ? info.title : info.name }}</li>
          <li>{{info.original_title  ? info.original_title : info.original_name }}</li>

          <li>  <!--da mettere require() meglio cosi perchè cosi agg solo la lingua giu |perchè è una stringa dinamica fatta da noi | gli fa lavorare come se fosse normale, e la fà ritornare un modulo bildato-->
             <img v-if="flag(info.original_language)"
                  :src="require(`@/assets/img/${info.original_language}.png`)" 
                  :alt="info.title">
               
          </li>
           <span>{{info.original_language}}</span>

          <li>{{info.vote_average}}</li>
       </ul>
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
img {
   width: 50px;
}

</style>