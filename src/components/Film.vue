<template>
   <div class="film">
       <ul>
           <li>{{info.title}}</li>
           <li>{{info.original_language}}</li>
       </ul>
   </div>
</template>

<script>
export default {
   name: 'Film',
   props:['info'],
}
</script>

<style>

</style>