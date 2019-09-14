<template lang="html">
   <div id="main">
      <h1>Studio Ghibli - Films</h1>
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
  </div>
</template>

<script>
import { eventBus } from "./main.js"
import FilmsList from "./components/FilmsList.vue"
import FilmDetail from "./components/FilmDetail.vue"

export default {
  name: "app",
  data() {
    return {
      films: [],
      selectedFilm: {}
    };
  },
  components: {
    "films-list": FilmsList,
    "film-detail": FilmDetail
  },
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('film-selected', (film) => {
      this.selectedFilm = film  
    })
  }
}
</script>

<style lang="css" scoped>
h1{
  text-align: center;
}

#main {
  background-color: green;
  background-image: url("../images/Studio_Ghibli_logo.png")
}
</style>
