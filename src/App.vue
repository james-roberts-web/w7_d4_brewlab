<template lang="html">
  <div>
    <h1>BOOOOOODOG LAB</h1>
      <div class="main-container">
        <beers-list :beers='beers'></beers-list>
        <beer-detail :beer='selectedBeer'></beer-detail>
        <beers-list :beers='favouriteBeers'></beers-list>
      </div>
  </div>

</template>

<script>

import BeersList from './components/BeersList.vue';
import ListItem from './components/ListItem.vue';
import BeerDetail from './components/BeerDetail.vue';

import { eventBus } from './main.js';

export default {
  name: 'app',
  data () {
    return {
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
    };
  },

  mounted () {
      fetch('https://api.punkapi.com/v2/beers')
      .then (res => res.json())
      .then (beers => this.beers = beers)

      eventBus.$on('beer-selected', (beer) => {
        this.selectedBeer = beer
      })
  },

methods: {
  addToFavourites: function() {
    this.favouriteBeer.push(this.selectedBeer)
  }
},
  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail,
  }
}


</script>


<style lang="css" scoped>
.main-container {
width: 1000px;
  display: flex;
  justify-content: space-between;
}
</style>
