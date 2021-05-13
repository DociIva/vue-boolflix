<template>
     <div class="cards-container">
            <section class="cards">
   
                <article class="card">
                    
                        <div class="image">
                           <img  v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`" alt="copertina">
                           <img v-else src="../assets/img/poster-placeholder.png" alt="">
                        </div>
                        <div class="card-content">
                           <h2>{{info.title ? info.title : info.name }}</h2>
                           <h3>{{info.original_title  ? info.original_title : info.original_name }}</h3>
                           <span>{{info.overview}}</span>

                           <div class="star">
                             <span>{{getStartVoto(info.vote_average)}}</span>
                             <i v-for="i in getStartVoto(info.vote_average)" 
                               :key="`full-${i}`" 
                               class="fas fa-star">
                            </i>
                             <i v-for="i in 5 - getStartVoto(info.vote_average)"
                               :key="`empthy-${i}`"
                               class="far fa-star">
                            </i>
                         </div> <!-- .star -->
                        </div><!-- .card-content -->
                        
                     
                </article><!-- .card -->
               </section><!-- .cards -->  
       </div><!-- .centered -->
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
      },
      getStartVoto(vote) {
         return Math.ceil(vote / 2);
      },
   }
   
}
</script>

<style scoped lang="scss">

.cards-container {
	flex: 1 1 300px;
   height: calc(100vh -57px);
	margin-top: 10px;
	padding: 10px;
   align-items: stretch;
}
.cards {
   display: flex;
   justify-content: center;
}
.card {
	flex: 0 1 20%;
   position: relative;
}

.card-content {
   background-color: lightcoral;
   width: 100%;
}


</style>