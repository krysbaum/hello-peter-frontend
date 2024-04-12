<script>
export default {
  props: {
    quotes: Array,
  },
};
</script>

<template>
  <div>
    <h1>All quotes</h1>
    <div v-for="quote in quotes" v-bind:key="quote.id">
      <h2>{{ quote.body }}</h2>
      <!-- <p>Rarity: {{ quote.rarity }}</p> -->
    </div>
  </div>
</template>

<style></style>
