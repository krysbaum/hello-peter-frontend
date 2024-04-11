<script>
export default {
  props: {
    photos: Array,
  },
};
</script>

<template>
  <div>
    <h1>All quotes</h1>
    <div v-for="quote in quotes" v-bind:key="quote.id">
      <h2>{{ quote.name }}</h2>
      <imag v0-bind:src="quote.url" />
      <p>Width: {{ quote.width }}</p>
      <p>Height: {{ quote.height }}</p>
    </div>
  </div>
</template>

<style></style>
