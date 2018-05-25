<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress-bar bg-success" :style="{width: (quoteCount * 10) + '%'}" role="progressbar"
             :aria-valuenow="quoteCount * 10" aria-valuemin="0"
             :aria-valuemax="100">
          {{ quoteCount }} / {{ maxQuotes }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['quoteCount', 'maxQuotes'],
  };
</script>

<style scoped>

</style>
