<template>
  <div>
    <h1>Our premium Beers <br> to go with your Pizza</h1>
    <br>
    <ul>
    <beer-list-item v-for="(beer, index) in beers" 
    :beer="beer" :key="index"></beer-list-item>
    </ul>
  
  </div>
</template>

<script>
import BeerListItem from "./BeerListItem.vue";

export default {
  name: "beer-list",
  props: ["beers"],
  components: {
    "beer-list-item": BeerListItem
  }
}
</script>

<style scoped>

</style>
