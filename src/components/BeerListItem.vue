<template>
  <div>
    <li @click="show">{{ beer.name }}: <br> {{ beer.tagline }}</li><br><br>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: "beer-list-item",
  props: ["beer"],
  methods: {
      show(){
          eventBus.$emit("beer-selected", this.beer);
      }
   }
}
</script>

<style scoped>

</style>