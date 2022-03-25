<template>
  <div id="app">
    <AppHeader @filtra="getGenre" :songs="songs" />
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
      songs: null,
    };
  },
  methods: {
    getGenre(selected) {
      this.selectedGenre = selected;
    },
    populeSongs(arrSongs) {
      this.songs = arrSongs;
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
