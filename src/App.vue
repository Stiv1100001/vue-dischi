<template>
  <div id="app" class="vw-100">
    <header class="vw-100 d-flex justify-content-between p-2">
      <img
        src="https://grafica-facile.com/wp-content/uploads/2022/01/spotify-logo.png"
        alt="Spotify logo"
        class="img-fluid"
      />
      <SearchBar
        @search="onSearch"
        :authors="authors"
        :genres="genres"
        @genre="setGenre"
        @author="setAuthor"
      />
    </header>
    <main class="vw-100 overflow-auto">
      <div class="container pt-5">
        <DiscList :filter="filter" @authors="onAuthors" @genre="onGenres" />
      </div>
    </main>
  </div>
</template>

<script>
import DiscList from "@/components/DiscList.vue";
import SearchBar from "./components/SearchBar.vue";
export default {
  name: "App",
  components: { DiscList, SearchBar },
  data: () => ({
    authors: [],
    genres: [],
    filter: {
      author: "",
      genre: "",
    },
  }),
  methods: {
    onSearch(e) {
      this.toSearch = e;
    },
    onAuthors(e) {
      this.authors = e;
    },
    onGenres(e) {
      this.genres = e;
    },
    setAuthor(e) {
      console.log(e);
      this.filter.author = e;
    },
    setGenre(e) {
      console.log(e);
      this.filter.genre = e;
    },
  },
};
</script>

<style lang="scss" scoped>
#app {
  max-width: 100vw;
}
header {
  height: 7vh;
  background-color: rgb(42, 52, 61);
}

main {
  min-height: 93vh;
  background-color: rgb(30, 45, 59);
}
</style>
