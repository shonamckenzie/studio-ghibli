<template lang="html">
  <div><h1>Studio Ghibli - Films</h1>
   <div id="main">     
      <films-list :films="films"></films-list>
      <film-detail :film="selectedFilm"></film-detail>
   </div>
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
      selectedFilm: null
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
  background-color: rgb(0, 77, 128);
  background-image: url("../images/Studio_Ghibli_logo.png");
  display: flex;
  justify-content: space-between;
  width: 85%;
  margin: 0 auto;
}
</style>
