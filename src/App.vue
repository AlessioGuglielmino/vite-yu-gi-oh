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
  <div class="wrapper">
    <div class="header"><AppHeader /></div>
    <AppMain />
  </div>
</template>

<style lang="scss" scoped>
.header {
  height: 100px;
}
</style>
