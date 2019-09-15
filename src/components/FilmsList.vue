<template lang="html">
    <div id="filmsList">
        <h2>Films</h2>
        <ul>
            <film-list-item v-for="(film, index) in films" :film="film" :key="index"></film-list-item>
        </ul>
    </div>
</template>

<script>
import FilmListItem from "../components/FilmListItem.vue"

export default {
    name: "films-list",
    props: ['films'],
    components: {
        "film-list-item": FilmListItem
    }
}
</script>

<style lang="css" scoped>
h2 {
    margin: 20px 5px 20px;
    padding: 5px;
    position: fixed;
}
#filmsList {
    height: 400px;
    overflow-y: scroll;
    border: 1px solid rgb(0, 77, 128);
  }

  #filmsList ul {
    margin-top: 70px;
    padding: 0;
  }

  ::-webkit-scrollbar {
    -webkit-appearance: none;
    width: 7px;
  }

  ::-webkit-scrollbar-thumb {
    border-radius: 4px;
    background-color: rgba(0,0,0,.5);
    -webkit-box-shadow: 0 0 1px rgba(255,255,255,.5);
  }
</style>
