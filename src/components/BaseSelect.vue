<script>
import axios from "axios";

export default {
  data() {
    return {
      archetypesSelected: "",
      archetypes: [],
    };
  },
  components: {},

  methods: {
    filterCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => {
          this.archetypes = response.data;
        });
    },
  },
  created() {
    this.filterCards();
  },

  emits: ["filter-submit"],
};
</script>

<template>
  <select
    @submit.prevent="$emit('filter-submit', archetypesSelected)"
    v-model="archetypesSelected"
    class="form-select"
    aria-label="Default select example"
  >
    <option selected>Filter Archetype</option>
    <option v-for="archetype in archetypes" :key="archetype" :value="archetype">
      {{ archetype.archetype_name }}
    </option>
  </select>
</template>

<style lang="scss" scoped>
select {
  width: 20%;
  padding: 10px;
  margin-left: 10px;
}
</style>
