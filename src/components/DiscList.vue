<template>
  <div class="row row-cols-5 justify-content-center">
    <MyLoader v-if="discList.length === 0" />
    <DiscCard v-for="(disc, index) in currentDiscList" :key="index" :disc="disc" />
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
  props: {
    filter: Object,
  },
  created() {
    setTimeout(() => {
      axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
        this.discList = res.data.response;

        const authors = this.discList.map((disc) => disc.author);
        const genre = Array.from(new Set(this.discList.map((disc) => disc.genre)));

        this.$emit("authors", authors);
        this.$emit("genre", genre);
      });
    }, 3000);
  },
  computed: {
    currentDiscList() {
      return this.discList
        .filter((disc) => disc.author.includes(this.filter.author))
        .filter((disc) => disc.genre.includes(this.filter.genre));
    },
  },
};
</script>

<style lang="scss" scoped></style>
