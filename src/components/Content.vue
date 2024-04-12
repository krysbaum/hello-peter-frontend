<script>
import axios from "axios";
import QuotesIndex from "./QuotesIndex.vue";
import QuotesNew from "./QuotesNew.vue";
import QuotesShow from "./QuotesShow.vue"
import Modal from "./Modal.vue"

export default {
  components: {
    // QuotesIndex,
    // QuotesNew,
    QuotesShow,
    Modal,
  },
  data: function () {
    return {
      quotes: [],
      currentQuote: {},
      isQuotesShowVisible: false,
    };
  },
  created: function () {
    this.handleShowQuote();
    //this.handleIndexQuotes();
  },
  methods: {
    // handleIndexQuotes: function () {
    //   axios.get("http://localhost:5000/quotes.json").then((response) => {
    //     console.log("quotes index", response);
    //     this.quotes = response.data;
    //   });
    // },
    // handleCreateQuote: function (params) {
    //   axios
    //     .post("http://localhost:5000/quotes.json", params)
    //     .then((response) => {
    //       console.log("quotes create", response);
    //       this.quotes.push(response.data);
    //     })
    //     .catch((error) => {
    //       console.log("quotes create error", error.response);
    //     });
    // },
    handleShowQuote: function () {
      axios.get("http://localhost:5000/quotes/random.json").then((response) => {
        console.log("quotes show", response);
        this.currentQuote = response.data;
        //this.isQuotesShowVisible = true;
      })
      // console.log("handleShowQuote");
      // this.currentQuote = response.data;
      
    },
    handleClose: function () {
      this.isQuotesShowVisible = false;
    },
  },
};
</script>

<template>
  <main>
    <img className="hello_peter_gif" height="300" src="https://media.tenor.com/sldhKegIadAAAAAi/hello-peter-otto-octavius.gif" alt="" />
    <br></br>
    <br></br>
    <br></br>
    <br></br>
    <br></br>
    <!-- <h1>Hello, Peter!</h1> -->
    <!-- <QuotesIndex v-bind:quotes="quotes" v-on:showQuote="handleShowQuote" /> -->
    <button class="btn btn-info" @click="handleShowQuote, isQuotesShowVisible = true">YOUR PETER QUOTE</button>
    <Modal class="modal" v-bind:show="isQuotesShowVisible" v-on:close="handleClose">
      <!--<QuotesShow v-bind:quote="currentQuote" />
      <QuotesShow v-bind:quote="currentQuote" v-on:showQuote="handleShowQuote" />-->
      <QuotesShow v-bind:quote="currentQuote" v-on:showQuote="handleShowQuote" />
    </Modal>
    <!-- <QuotesShow v-bind:quote="currentQuote" v-on:showQuote="handleShowQuote" /> -->
    <!-- <QuotesShow v-on:showQuote="handleShowQuote" /> -->
    <QuotesNew v-on:createQuote="handleCreateQuote" />
  </main>
</template>

<style></style>
