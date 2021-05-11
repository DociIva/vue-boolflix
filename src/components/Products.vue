<template>
  <div class="container">
      <ul>
        <li>{{movies.title}}</li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'Products',
  props: ['movies']
}
</script>

<style scoped lang="scss">

</style>