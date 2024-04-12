<script>
import axios from "axios";
import QuotesIndex from "./QuotesIndex.vue";
import QuotesNew from "./QuotesNew.vue";

export default {
  components: {
    QuotesIndex,
    QuotesNew,
  },
  data: function () {
    return {
      quotes: [],
    };
  },
  created: function () {
    this.handleIndexQuotes();
  },
  methods: {
    handleIndexQuotes: function () {
      axios.get("http://localhost:5000/quotes.json").then((response) => {
        console.log("quotes index", response);
        this.quotes = response.data;
      });
    },
    handleCreateQuote: function (params) {
      axios
        .post("http://localhost:5000/quotes.json", params)
        .then((response) => {
          console.log("quotes create", response);
          this.quotes.push(response.data);
        })
        .catch((error) => {
          console.log("quotes create error", error.response);
        });
    },
  },
};
</script>

<template>
  <main>
    <h1>Hello, Peter!</h1>
    <QuotesIndex v-bind:quotes="quotes" />
    <img className="hello_peter_gif" height="300" src="https://media.tenor.com/sldhKegIadAAAAAi/hello-peter-otto-octavius.gif" alt="" />
    <br></br>
    <br></br>
    <QuotesNew v-on:createQuote="handleCreateQuote" />
  </main>
</template>

<style></style>
