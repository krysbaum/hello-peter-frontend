<script>
export default {
  data: function () {
    return {
      newQuoteParams: {},
    };
  },
  methods: {
    handleSubmit: function () {
      this.$emit("createQuote", this.newQuoteParams);
      this.newQuoteParams = {};
    },
  },
};
</script>

<template>
  <div>
    <h1>New Quote</h1>
    <form v-on:submit.prevent="handleSubmit">
      <div>
        Name:
        <input type="text" v-model="newQuoteParams.name" />
      </div>
      <div>
        Url:
        <input type="text" v-model="newQuoteParams.url" />
      </div>
      <div>
        Width:
        <input type="text" v-model="newQuoteParams.width" />
      </div>
      <div>
        Height:
        <input type="text" v-model="newQuoteParams.height" />
      </div>
      <button type="submit">Create Peter Quote</button>
    </form>
  </div>
</template>

<style></style>
