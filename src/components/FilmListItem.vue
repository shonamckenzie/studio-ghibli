<template lang="html">
  <li>{{ film.title }}</li>
</template>

<script>
export default {
    name: "film-list-item",
    props: ['film']
}
</script>

<style lang="css" scoped>

</style>