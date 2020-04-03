<template lang="html">
  <div v-if='beer'>
    <h3>{{beer.name}}</h3>
    <p>Tagline: {{beer.tagline}}</p>
    <p>Description: {{beer.description}}</p>
    <p>Brewers'tips: {{beer.brewers_tips}}</p>
    <img :src="beer.image_url" alt="A BEER!">
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style scoped>

</style>