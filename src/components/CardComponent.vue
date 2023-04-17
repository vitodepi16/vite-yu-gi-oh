<template>
  <div class="col-12 col-sm-6 col-md-4 col-lg-3 p-3 mt-2">
    <div class="card text-center">
      <div class="card-head">
        <img :src="card.card_images[0].image_url" />
      </div>
      <div class="card-body">
        <h4 class="text-white">{{ card.name }}</h4>
        <div>{{ card.archetype }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: ["card"],
};
</script>

<style lang="scss" scoped>
@use "../assets/partials/variables" as *;
img {
  width: 100%;
}
.card-body {
  background-color: $my-bg;
}
.card {
  background-color: white;
}
</style>
