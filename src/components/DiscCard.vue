<template>
  <div id="card" class="col pt-3 text-center">
    <img :src="disc.poster" :alt="disc.title" class="img-fluid mb-3" />
    <h5 class="text-white mb-5">{{ disc.title }}</h5>
    <h6>{{ disc.author }}</h6>
    <h6 class="mb-5">{{ disc.year }}</h6>
  </div>
</template>

<script>
export default {
  name: "DiscCard",
  props: {
    disc: Object,
  },
};
</script>

<style lang="scss" scoped>
#card {
  background-color: rgb(46, 58, 70);
  // width: calc(100% / 5);

  img {
    // height: 50%;
    object-fit: cover;
  }

  h6 {
    color: #7c7f80;
  }
}
</style>
