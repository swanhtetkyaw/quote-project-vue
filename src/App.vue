<template>
  <div class="container">
    <app-progress :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-progress>
    <app-new-quote @addNewQuote="addQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @clickedQuote="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Click the box to delete</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuotGrid.vue";
import NewQuote from "./components/newQuote.vue";
import Progress from "./components/progressHeader.vue";
export default {
  name: "App",
  data() {
    return {
      quotes: [
        {
          quoteContent: "Be yourself; everyone else is already taken.",
          author: "Oscar Wilde"
        }
      ],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appProgress: Progress
  },
  methods: {
    addQuote(quote) {
      if (quote.quoteContent) {
        if (this.quotes.length >= 10) {
          return alert("Delete one or more quotes to add more!");
        }
        this.quotes.push(quote);
      }
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
