<template lang="html">
   <div id="main">
      <h1>Studio Ghibli - Films</h1>
      <films-list :films="films"></films-list>
  </div>
</template>

<script>
import FilmsList from "./components/FilmsList"


export default {
  name: "app",
  data() {
    return {
      films: []
    }
  },
  components: {
    "films-list": FilmsList
  },
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)
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
