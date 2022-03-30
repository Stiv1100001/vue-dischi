<template>
  <div id="app">
    <header class="vw-100 d-flex p-2">
      <img
        src="https://grafica-facile.com/wp-content/uploads/2022/01/spotify-logo.png"
        alt="Spotify logo"
        class="img-fluid"
      />
    </header>
    <main class="vw-100 overflow-auto">
      <div class="container pt-5">
        <DiscList />
      </div>
    </main>
  </div>
</template>

<script>
import DiscList from "@/components/DiscList.vue";
export default {
  name: "App",
  components: { DiscList },
};
</script>

<style lang="scss">
header {
  height: 7vh;
  background-color: rgb(42, 52, 61);
}

main {
  min-height: 93vh;
  background-color: rgb(30, 45, 59);
}
</style>
