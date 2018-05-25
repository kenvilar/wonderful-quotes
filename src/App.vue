<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a quote to delete
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue';
  import VueSweetalert2 from 'vue-sweetalert2';

  Vue.use(VueSweetalert2);
  import QuoteGrid from './components/QuoteGrid';
  import NewQuote from './components/NewQuote';

  export default {
    data() {
      return {
        quotes: [
          'Just a Quote to see something',
        ],
        maxQuotes: 10,
      };
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
    },
    methods: {
      newQuote(quote) {
        if (quote) {
          this.quotes.push(quote);
        }
      },
    },
  };
</script>

<style>
</style>
