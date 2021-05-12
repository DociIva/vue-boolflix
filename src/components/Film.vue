<template>
   <div class="film">
       <ul>
          <li>{{info.title}}</li>
          <li>{{info.original_title}}</li>
          <li>{{info.original_language}}</li>
          <li>{{info.vote_average}}</li>
       </ul>
   </div>
</template>

<script>
export default {
   name: 'Film',
   props: {
      info: Object,
   }
   
}
</script>

<style scoped lang="scss">

</style>