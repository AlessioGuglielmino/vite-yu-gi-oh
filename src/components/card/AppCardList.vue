<script>
import axios from "axios";
import AppCard from "./AppCard.vue";
import BaseSelect from "../BaseSelect.vue";

export default {
  data() {
    return {
      cards: [],
    };
  },
  components: { AppCard, BaseSelect },
  methods: {
    fetchCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((response) => {
          this.cards = response.data.data;
        });
    },
  },

  created() {
    this.fetchCards();
  },
};
</script>

<template>
  <BaseSelect />

  <div class="container">
    <div class="row g-2 row-cols-2 row-cols-md-3 row-cols-lg-4">
      <AppCard
        v-for="card in cards"
        :image_url_small="card.card_images[0].image_url_small"
        :name="card.name"
        :archetype="card.archetype"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
