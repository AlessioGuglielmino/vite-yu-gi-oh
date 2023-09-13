<script>
export default {
  props: {
    image_url_small: String,
    name: String,
    archetype: String,
  },

  data() {
    return {};
  },
};
</script>

<template>
  <div class="col text-center carta g-3">
    <img :src="image_url_small" alt="" />

    <div class="card-name">{{ name }}</div>
    <div v-if="archetype" class="card-archetype">
      {{ archetype }}
    </div>
    <div v-else>
      <p>Not Defined</p>
    </div>
  </div>
</template>

<style lang="scss">
.carta {
  background-color: orange;
}
.card-name {
  font-weight: bolder;
  color: white;
}

.card-archetype {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: bolder;
}

p {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: bolder;
}
</style>
