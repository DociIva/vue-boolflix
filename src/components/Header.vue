<template>
   <header class="flex">
      <!--per il logo-->
      <a href="#">Logo</a>

      <!--ricerca-->
      <div class="search">                                                <!--funzione fatta sotto-->
        <input type="text" placeholder="Cerca il tuo film / serie" v-model.trim="searchText">
        <!--EVENTO tuo PER TRASMETTERE I DATI DAL FIGLIO AL PAPA ('nome', funzione che ottiene i dati da mettere ora nell'APP)-->
        <button @click="$emit('search',searchText)"
               class="ricerca">Ricerca</button>
      </div>
   </header>
   
</template>

<script>


export default {
   name:'Header',
   data() {
      return { 
         // dato di raccoglimento
         searchText: '',
      }
   },
   methods: {
      
   },
}
</script>

<style scoped lang="scss">

.flex {
   display: flex;
   justify-content: space-between;
   align-items: center;
}
.ricerca {
   margin-top: 20px;
   padding-right: 40px;
   padding-left: 40px;
}
input {
   padding: 10px;
}
button {
   padding: 10px;
}

</style>