<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },
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
  <div class="container">
    <div class="row g-4 row-cols-2 row-cols-md-3 row-cols-lg-4">
      <div class="col text-center" v-for="card in cards">
        <img :src="card.card_images[0].image_url_small" alt="" />

        <div class="card-name">{{ card.name }}</div>
        <div class="card-archetype">
          {{ card.archetype }}
        </div>
        <div class="card-race">
          {{ card.race }}
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card-name {
  font-weight: bolder;
  color: white;
}
</style>
