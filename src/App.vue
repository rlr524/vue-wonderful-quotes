<template>
  <div id="app" class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteSelectedQuote"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import NewQuote from "@/components/NewQuote.vue";
import QuoteGrid from "@/components/QuoteGrid.vue";

export default {
  name: "App",
  components: {
    appHeader: Header,
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid,
  },
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10,
    };
  },
  methods: {
    newQuote: function(quote) {
      if (this.quotes.length < this.maxQuotes) {
        this.quotes.push(quote);
      } else {
        return alert(
          `Maximum quotes is ${this.maxQuotes}. Please delete a quote before adding a new one.`
        );
      }
    },
    deleteSelectedQuote: function(index) {
      this.quotes.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  margin-top: 2em;
  font-size: 16px;
}
</style>
