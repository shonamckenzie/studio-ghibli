<template lang="html">
  <li v-on:click="handleClick">{{ film.title }}</li>
</template>

<script>
import { eventBus } from "../main.js"

export default {
    name: "film-list-item",
    props: ['film'],
    methods: {
        handleClick(){
            eventBus.$emit('film-selected', this.film)
            
        }
    }
}
</script>

<style lang="css" scoped>
li {
    list-style-type: none;
    display: block;
    font-size: 16px;
    margin: 10px 0;
    padding: 10px;
    cursor: pointer;
    color: black;
    transition: 0.1s all ease-in;
  }

  li:hover {
    background: #dbe8ff;
    color: #222;
  }
</style>