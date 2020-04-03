<template>
  <div id="app">
    <h1>BREWDOG</h1>
    <h2>Pizza Favourites</h2>
    
    <beer-list :beers="beers"></beer-list>
    <beer-detail :beer="selectedBeer"></beer-detail>

    <!-- <select v-model="selectedBeer">
      <option disabled value="">Select a Beer</option>
      <option v-for="(beer, index) in beers" 
        :beer="beer" :key="index">{{beer}}
      </option>
    </select> -->
  </div>
</template>

<script>
import BeerList from "./components/BeerList.vue";
import BeerDetail from './components/BeerDetail.vue';
import { eventBus } from "./main.js";

export default {
  name: 'app',
   data() {
    return {
      beers: [],
      selectedBeer: null
    };
  },
  mounted() {
    this.get();
    eventBus.$on("beer-selected", (beer) => {this.selectedBeer = beer});
  },
  methods: {
    get: function() {
    fetch('https://api.punkapi.com/v2/beers/?food=pizza')
    .then(res => res.json())
    .then(beers => this.beers = beers)
    }
  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail
  }
}
 
</script>

<style>
#app {
  font-family: 'Lato', sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  /* list-style-type: none; */
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
  color: green;
}
</style>
