<template>
  <div id="app">
    <AppHeader @filtra="getGenre" :genres="genres" :authors="authors" />
    <AppMain :selectedGenre="selectedGenre" @populeSelect="populeSongs" />
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
      selectedGenre: "",
      genres: null,
      authors: null,
    };
  },
  methods: {
    getGenre(selected) {
      this.selectedGenre = selected;
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
