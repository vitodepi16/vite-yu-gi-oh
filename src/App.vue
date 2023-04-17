<template>
  <div>
    <HeaderComponent />
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
import HeaderComponent from "./components/HeaderComponent.vue";
export default {
  name: "App",
  components: {
    HeaderComponent,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCard() {
      const url = store.baseUrl + store.endPoint;
      axios.get(url).then((res) => { console.log(res); });
    },
  },
  mounted() {
    store.endPoint = "cardinfo.php?num=50&offset=0";
    this.getCard();
  },
};
</script>

<style lang="scss" scoped></style>
