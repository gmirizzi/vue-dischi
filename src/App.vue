<template>
  <div id="app">
    <AppHeader @filtra="getFilter" :genres="genres" :authors="authors" />
    <AppMain :selectedFilter="selectedFilter" @populeSelect="populeSongs" />
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      selectedFilter: "",
      genres: null,
      authors: null,
    };
  },
  methods: {
    getFilter(selected) {
      this.selectedFilter = selected;
    },
    populeSongs(arrSongs) {
      this.genres = [...new Set(arrSongs.map((song) => song.genre))].sort();
      this.authors = [...new Set(arrSongs.map((song) => song.author))].sort();
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
#app {
  background-color: #1e2d3bff;
  min-height: 100vh;
}
</style>
