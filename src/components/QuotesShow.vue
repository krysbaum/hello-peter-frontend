<script>
export default {
  props: {
    quote: Object,
  },
};
</script>

<template>
  <div>
    <h1>Your Peter Quote is:</h1>
    <h1>{{ quote.body }}</h1>
    <!-- <p>Rarity: {{ quote.rarity }}</p> -->
  </div>
</template>

<style></style>
