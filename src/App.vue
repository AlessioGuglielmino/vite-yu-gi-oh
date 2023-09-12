<script>
import AppMain from "./components/AppMain.vue";
import AppHeader from "./components/AppHeader.vue";
import AppCard from "./components/card/AppCard.vue";

export default {
  data() {
    return {};
  },

  components: { AppMain, AppHeader, AppCard },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss" scoped></style>
