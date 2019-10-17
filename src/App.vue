<template lang="html">
  <div>
    <h1>BOOOOOODOG LAB</h1>
    <beers-list :beers='beers'></beers-list>
  </div>
</template>

<script>

import BeersList from './components/BeersList.vue';
import ListItem from './components/ListItem.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data () {
    return {
      beers: []
    };
  },

  mounted () {
      fetch('https://api.punkapi.com/v2/beers')
      .then (res => res.json())
      .then (beers => this.beers = beers)
  },

  components: {
    "beers-list": BeersList
  }
}


</script>


<style lang="css" scoped>
</style>
