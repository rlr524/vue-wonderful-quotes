<template>
  <div class="row">
    <app-quote v-for="(quote, index) in quotes" :key="index">
      {{ quote }}
    </app-quote>
  </div>
</template>

<script>
import Quote from "@/components/Quote.vue";

export default {
  name: "QuoteGrid",
  components: {
    appQuote: Quote,
  },
  props: {
    quotes: {
      type: Array,
      required: false,
    },
  },
};
</script>

<style scoped></style>
