<script>
import AppCardList from "./card/AppCardList.vue";

export default {
  data() {
    return {};
  },
  components: { AppCardList },
};
</script>

<template>
  <!-- BOTTONE PER FILTRO RICERCA -->
  <div class="container">
    <!-- IMPORTO APP CARD LIST  -->
    <main><AppCardList /></main>
  </div>
</template>

<style lang="scss" scoped>
main {
  background-color: orange;
}
</style>
