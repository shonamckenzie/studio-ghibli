<template lang="html">
  <div>
      <h3>{{ film.title }}</h3>
      <p>Director: {{ film.director }}</p>
      <p>Release Date: {{film.release_date }}</p>
      <p>Description: {{ film.description }}</p>
      <p>Rotten Tomatoes Score: {{ film.rt_score }}</p>
  </div>
</template>

<script>
export default {
    name: 'film-detail',
    props: ['film']
}
</script>

<style lang="css" scoped>

</style>