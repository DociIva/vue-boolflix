<template>
  <div class="container flex">
      <div>
          <!--Logo  <img src="../assets/logo.png" alt=""> -->
          
      </div>
      <!--SEARCH E BUTTON-->
     
       <!-- The form -->
     <form class="ricerca">
        <input type="text" placeholder="Cerca il tuo film" name="search" v-model.trim="searchText" >
         <!-- .prevent l'evento di invio non ricaricherà più la pagina -->
        <button type="button" placeholder="cerca il tuo film" @click="$emit('aggSearchText', searchText)">CERCA </button>
     </form>
  
      
  </div>
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
/*
.flex {
   display: flex;
   justify-content: space-between;
   align-items: center;
}*/
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