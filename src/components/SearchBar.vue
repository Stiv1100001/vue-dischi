<template>
  <div class="d-flex">
    <select v-model="authorToSearch">
      <option value="" @click="$emit('author', authorToSearch)">Nessuno</option>
      <option
        v-for="author in authors"
        :key="author"
        :value="author"
        @click="$emit('author', authorToSearch)"
      >
        {{ author }}
      </option>
    </select>
    <select v-model="genreToSearch" class="ms-3">
      <option value="" @click="$emit('genre', genreToSearch)">Nessuno</option>
      <option
        v-for="genre in genres"
        :key="genre"
        :value="genre"
        @click="$emit('genre', genreToSearch)"
      >
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  data: () => ({
    genreToSearch: "",
    authorToSearch: "",
  }),
  props: {
    authors: Array,
    genres: Array,
  },
};
</script>

<style></style>
