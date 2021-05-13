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
                           <h2>{{info.original_title  ? info.original_title : info.original_name }}</h2>
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
	margin-top: 10px;
	padding: 10px;
   max-height: 600px;
   max-width: 100%;
   
}
.cards {
   display: flex;
   justify-content: center;
}
.card {
	flex: 0 1 20%;
   position: relative;
   box-shadow: 5px 5px 15px #dedede;
}

.card-content {
   opacity: 0;
   position: absolute;
   top: 0;
   left: 0;
   right:0;
   bottom: 0;
   color: #fff;
   font-size: 14px;
   background-color: rgb(2, 7, 21);
   box-shadow: 0 0 12px hsl(203, 48%, 68%);
   width: 100%;
   height: 100%;
   padding: 60px;
   text-align: center;
   transition: 0.5s;
   &:hover {
      opacity: 1;
      cursor: pointer;
   }
}
.star {
   color:rgb(250, 250, 112);
}

h2,
span {
   margin: 5px;
}

.image {
   max-width: 100%;
   max-height: 600px;
}
</style>