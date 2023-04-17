<template>
  <div class="container p-4">
    <div class="row">
      <CardComponent
        v-for="card in store.cardList"
        :key="card.id"
        :card="card"
      />
    </div>
  </div>
</template>

<script>
import { store } from "../../data/store";
import CardComponent from "../components/CardComponent.vue";
export default {
  name: "MainComponent",
  components: {
    CardComponent,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/partials/variables" as *;

.container {
  background-color: $my-bg;
}
.row {
  background-color: white;
}
</style>
