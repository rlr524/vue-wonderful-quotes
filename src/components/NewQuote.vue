<template>
  <div class="row">
    <form>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
      >
        <label for="submit-quote">Quote</label>
        <textarea
          name="submit-quote"
          class="form-control"
          rows="3"
          v-model="quote"
        ></textarea>
      </div>
      <div
        class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
      >
        <button class="btn btn-primary" @click.prevent="createNew">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "NewQuote",
  data: function() {
    return {
      quote: "",
    };
  },
  methods: {
    createNew: function() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    },
  },
};
</script>

<style scoped></style>
