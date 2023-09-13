<script>
import axios from "axios";

export default {
  data() {
    return {
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

          console.log(this.archetypes);
        });
    },
  },
  created() {
    this.filterCards();
  },
};
</script>

<template>
  <select class="form-select" aria-label="Default select example">
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
