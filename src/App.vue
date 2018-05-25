<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
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
  import Header from './components/Header';

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
      appHeader: Header,
    },
    methods: {
      newQuote(quote) {
        if (quote && this.quotes.length !== 10) {
          this.$swal({
            position: 'center',
            type: 'success',
            title: 'Your quote has been saved',
            showConfirmButton: true,
          }).then(() => {
            this.quotes.push(quote);
          });
        } else if (this.quotes.length === 10) {
          this.$swal({
            type: 'error',
            title: 'Oops...',
            text: 'You have a maximum of 10 quotes. Please delete first the quotes!',
          });
        }
      },
    },
  };
</script>

<style>
</style>
