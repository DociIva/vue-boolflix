<template>
   <header class="top-bar">
      <!--per il logo-->
      <a href="#">
         <img src="@/assets/img/Logo.png" alt="BoolFlix Logo">
      </a>

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

.top-bar{
   height: 120px;
   background-color: #000;
   padding: 0 60px;
   display: flex;
   justify-content: space-between;
   align-items: center;
}
.search {
   box-shadow: 5px 5px 20px hsl(218, 81%, 70%);
}
img {
   box-shadow: 5px 5px 20px hsl(218, 81%, 70%);
}
input {
   padding: 10px;
   border: 1px solid hsl(218, 81%, 70%);;
}
button {
   cursor: pointer;
   padding: 10px;
   color: #fff;
   background-color: rgb(230, 23, 23);
   transition: background 0.4s;
   &:hover {
      background-color: rgb(17, 40, 157);
   }
}

</style>