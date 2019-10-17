<template lang="html">
  <h1>BOOOOOODOG LAB</h1>
</template>

<script>
import { eventBus } from './main.js';

export default {
  name: 'app',
  data () {
    return {
      beers: []
    };
  },

  mounted () {
    this.getBeers()
  },

  methods : {
    getBeers: function () {
      fetch('https://api.punkapi.com/v2/beers')
      .then (res => res.json())
      .then (beers => this.beers = beers)
    }
  }
}
</script>


<style lang="css" scoped>
</style>
