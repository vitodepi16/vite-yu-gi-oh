<template>
  <div>
    <header>
      <HeaderComponent />
    </header>
    <main>
      <MainComponent/>
    </main>
  </div>
</template>

<script>
import axios from "axios";
import { store } from "../data/store.js";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from './components/MainComponent.vue'

export default {
  name: "App",
  components: {
    HeaderComponent,MainComponent
    
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCard() {
      const url = store.baseUrl + store.endPoint;
      axios.get(url).then((res) => { console.log(res.data );
      store.cardList = res.data });
    },
  },
  mounted() {
    store.endPoint = "cardinfo.php?num=50&offset=0";
    this.getCard();
  },
};
</script>

<style lang="scss" scoped></style>
