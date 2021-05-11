<template>
  <main>
    <div class="movie" v-for="movie in movies" :key="movie.id">
      <Film :info="movie" />
    </div>
  </main>
</template>

<script>

import Film from '@/components/Film.vue';
export default {
  name: 'Products',
  components: {
    Film,
  },
  props: ['movies'],
    
} 
</script>

<style scoped lang="scss">
main {
  height: 500px;
}
.movie {
  width: 200px;
  height: 300px;
}
</style>