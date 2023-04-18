<template>
  <div>
    <header>
      <HeaderComponent />
    </header>
    <main>
      <MainComponent />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCard() {
      const url = store.baseUrl + store.endPoint;
      let options = {};
      let params = {};
      for (let key in store.filter) {
        if (store.filter[key]) {
          params[key] = store.filter[key];
        }
      }

      if (Object.keys(params).length > 0) {
        options.params = params;
      }

      axios.get(url, options).then((res) => {
        store.cardList = res.data.data;
      });
    },
  },
  mounted() {
    store.endPoint = "cardinfo.php?num=50&offset=0";
    this.getCard();
  },
};
</script>

<style lang="scss" scoped></style>
