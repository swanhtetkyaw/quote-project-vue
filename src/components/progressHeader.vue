<template>
  <div class="row">
    <h3>Quotes</h3>
    <div class="col-sm-12">
      <div class="progress">
        <div
          class="progress-bar progress-bar-striped"
          role="progressbar"
          :style="{width: (quoteCount / maxQuotes) * 100 + '%'}"
          aria-valuenow="0"
          aria-valuemin="0"
          aria-valuemax="100"
        >{{quoteCount}} \ {{maxQuotes}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quoteCount", "maxQuotes"]
};
</script>

<style>
</style>