<template>
  <main>
     <section  v-show="filmList.length > 0" class="film">
        <h2>MOVIES</h2>
        <div class="cards">
            <!--loop qua nella :key="a + 1 se hai lo stetta key"--->
           <Film v-for="film in filmList" 
                 :key="film.id" 
                 :info="film"
            />

        </div>
     </section>

     <section v-show="series.length" class="serie-tv">
        <h2>SERIE TV</h2>
         
          <div class="cards">
            <!--loop qua nella :key="a + 1 se hai lo stetta key"--->
           <Film v-for="serie in series" 
                 :key="serie.id" 
                 :info="serie"
            />
        </div>
     </section>
  </main>
</template>

<script>

import Film from '@/components/Film.vue';
export default {
  name: 'Products',
  components: {
    Film,
  },
  // per portare i dati dal padre al figlio
  props: {    // per dire di che genere è
      filmList: Array,
      series: Array,
  }
  
} 
</script>

<style scoped lang="scss">

.cards {
  display: flex;
  flex-wrap: wrap;
  align-items: stretch;
}
h2 {
  color: rgba(194, 17, 17, 0.8);
  text-align: center;
  margin: 20px;
  font-size: 40px;
  &:hover {
    cursor: pointer;
  }
}






</style>