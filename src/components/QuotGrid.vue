<template>
  <div class="row mt-5">
    <app-quote v-for="(quote,index) in quotes" :key="index" @click.native="deleteQuote(index)">
      <template v-slot:content>{{quote.quoteContent}}</template>
      {{quote.author}}
    </app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("clickedQuote", index);
    }
  }
};
</script>

<style>
</style>