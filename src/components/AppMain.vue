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
  <main><AppCardList /></main>
</template>

<style lang="scss" scoped>
main {
  background-color: orange;
  min-height: 500px;
}
</style>
