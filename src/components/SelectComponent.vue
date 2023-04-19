<template>
  <div class="container p-4 ms-0">
    <select
      @change.prevent="changetype()"
      class="form-select"
      aria-label=""
      v-model="store.filter.archetype"
    >
      <option selected value="">All</option>
      <option
        v-for="(archetype, index) in statusOptions"
        :key="index"
        :value="archetype.archetype_name"
      >
        {{ archetype.archetype_name }}
      </option>
    </select>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../../data/store";
export default {
  name: "SelectComponent",
  data() {
    return {
      store,
      statusOptions: [],
    };
  },
  methods: {
    changetype() {
      this.$emit("filter");
      console.log(store.filter);
    },
  },
  mounted() {
    axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php").then((res) => {
      this.statusOptions = res.data;
    });
  },
};
</script>

<style lang="scss" scoped>
.form-select {
  width: 30%;
}
</style>
