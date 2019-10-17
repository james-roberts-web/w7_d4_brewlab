<template lang="html">
  <div v-if='beer'>
    <h2>{{ beer.name }}</h2>
    <h3>ABV: {{ beer.abv }}</h3>
    <h3>Tagline: {{ beer.tagline }}</h3>
    <button v-on:click='handleAddFavourite'>Add to favourites</button>
  </div>


</template>

<script>
import { eventBus } from '../main.js';
export default {
  name: 'beer-detail',
  props: ['beer'],
  methods: {
    handleAddFavourite() {
      eventBus.$emit('beer-selected', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
