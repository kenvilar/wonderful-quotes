<template>
  <div class="row">
    <app-quote v-for="(quote, index) in quotes" :key="quote" @click.native="removeQuote(index)">{{ quote }}</app-quote>
  </div>
</template>

<script>
  import Quote from './Quote';

  export default {
    props: ['quotes'],
    components: {
      appQuote: Quote,
    },
    methods: {
      removeQuote(quoteIndex) {
        this.quotes.splice(quoteIndex, 1);
      },
    }
  };
</script>

<style scoped></style>
