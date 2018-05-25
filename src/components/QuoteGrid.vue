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
        this.$swal({
          title: 'Are you sure you want to delete this quote?',
          type: 'warning',
          showCancelButton: true,
          confirmButtonText: 'Yes, delete it!',
          cancelButtonText: 'No, keep it',
        }).then((result) => {
          if (result.value) {
            this.$swal(
              'Deleted!',
              'Your quote has been deleted.',
              'success',
            );
            this.quotes.splice(quoteIndex, 1);
          } else if (result.dismiss) {
            this.$swal(
              'Cancelled',
              'Your quote is safe :)',
              'error',
            );
          }
        });
      },
    },
  };
</script>

<style scoped></style>
