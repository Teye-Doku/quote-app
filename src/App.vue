<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuoutes="maxQuotes"></app-header>
    <app-new-quote @addQuote="newQuote"></app-new-quote>
    <app-quote-grid @deletedQuote="deleteQuote" :quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";
export default {
  data() {
    return {
      quotes: ["just say something to see"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >=10){
          return alert('delete quote before adding another one');
      }  
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
