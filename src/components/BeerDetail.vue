<template lang="html">
  <div v-if='beer'>
    <h2>{{ beer.name }}</h2>
    <h3>ABV: {{ beer.abv }}</h3>
  </div>


  <!-- <p>BEERSH BEERSH BEERSH BEERSH BEERSH</p> -->
</template>

<script>
import { eventBus } from '../main.js';
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
