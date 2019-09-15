<template lang="html">
  <form v-on:submit.prevent>
      <input type="text" v-model="search" placeholder="search for film..." v-on:keyup="searchForFilm">
  </form>
</template>

<script>
import {eventBus} from '../main.js'

export default {
    name: "film-filter",
    data() {
        return {
            "search": "",
            "selectedFilm": {},
        }
    },
    props: ["films"],
    methods: {
        searchForFilm(){
            let foundFilm = this.films.find((film) => {
                return film.title.toLowerCase().indexOf(this.search.toLowerCase() > -1)
            })
            this.selectedFilm = foundFilm   
            eventBus.$emit('film-selected', this.selectedFilm)
        }
    }
}
</script>

<style lang="css" scoped>

</style>