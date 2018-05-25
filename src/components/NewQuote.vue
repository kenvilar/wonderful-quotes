<template>
  <div class="row">
    <form action="">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-2 form-group">
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-6 offset-md-2 form-group">
        <button class="btn btn-primary" @click.prevent="addQuote">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        quote: '',
      };
    },
    methods: {
      addQuote() {
        //todo
      }
    }
  };
</script>

<style scoped>

</style>
