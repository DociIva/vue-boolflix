<template>
  <div id="app">
    <!--header-->
    <header>
      <Header />
    </header>
    

    <!--content-->
    <main>
      <Products />
    </main>
    
  </div>
</template>

<script>
// IMPORTAZIONE DEI COMPONENTI
import Header from '@/components/Header.vue';
import Products from '@/components/Products.vue';

export default {
  name: 'App',
  components: {
    Header,
    Products,
  }
}
</script>

<style lang="scss">
@import '@/styles/general';

</style>
