<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <!-- <label for="quote">Quote</label> -->
        <textarea
          class="form-control"
          id="quote"
          rows="3"
          placeholder="Enter Quote..."
          v-model="quoteContent"
        ></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <input type="text" class="form-control" placeholder="Author" v-model="author" />
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button class="btn btn-primary" @click.prevent="addQuote">Save Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quoteContent: "",
      author: ""
    };
  },
  methods: {
    addQuote() {
      let quote = {
        quoteContent: this.quoteContent,
        author: this.author || "unknown"
      };
      this.$emit("addNewQuote", quote);
      this.quoteContent = "";
      this.author = "";
    }
  }
};
</script>

<style>
</style>