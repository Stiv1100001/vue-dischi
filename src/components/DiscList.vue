<template>
  <div class="row row-cols-5 justify-content-center">
    <MyLoader v-if="discList.length === 0" />
    <DiscCard v-for="(disc, index) in discList" :key="index" :disc="disc" />
  </div>
</template>

<script>
import axios from "axios";
import DiscCard from "./DiscCard.vue";
import MyLoader from "./MyLoader.vue";
export default {
  name: "DiscList",
  components: { DiscCard, MyLoader },
  data: () => ({
    discList: [],
  }),
  created() {
    setTimeout(() => {
      axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
        this.discList = res.data.response;
      });
    }, 3000);
  },
};
</script>

<style lang="scss" scoped></style>
