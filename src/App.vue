<template>
  <div id="app" class="container">
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "@/components/QuoteGrid.vue";

export default {
  name: "App",
  components: {
    appQuoteGrid: QuoteGrid,
  },
  data: function() {
    return {
      quotes: [
        "Never forget who you are, for surely the world will not. Make it your strength. Then it can never be your weakness. Armour yourself in it, and it will never be used against you.",
      ],
      maxQuotes: 10,
    };
  },
};
</script>

<style></style>
