<script>
import axios from "axios";
import AppCard from "./AppCard.vue";

export default {
  data() {
    return {
      cards: [],
    };
  },
  components: { AppCard },
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
  <div class="dropdown filter">
    <button
      class="btn btn-secondary dropdown-toggle"
      type="button"
      data-bs-toggle="dropdown"
      aria-expanded="false"
    >
      Archetype
    </button>
    <ul class="dropdown-menu">
      <li><a class="dropdown-item" href="#">Action</a></li>
      <li><a class="dropdown-item" href="#">Another action</a></li>
      <li><a class="dropdown-item" href="#">Something else here</a></li>
    </ul>
  </div>

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

<style lang="scss" scoped>
.filter {
  padding-top: 20px;
  margin: 20px;
}
</style>
