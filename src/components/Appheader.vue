<script>
export default {
  data() {
    return {
      title: " Yu-Gi-Oh API",
    };
  },
};
</script>

<template>
  <div class="header">
    <h1>
      <img src="../../public/Yu-Gi-Oh!.png" alt="" />
      {{ title }}
    </h1>
  </div>
</template>

<style lang="scss" scoped>
.header {
}
h1 {
  font-family: Arial, Helvetica, sans-serif;

  img {
    height: 50px;
  }
}
</style>
