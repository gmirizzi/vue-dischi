<template>
  <div id="app">
    <AppHeader @filtra="getGenre" />
    <AppMain :selectedGenre="selectedGenre" />
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
    };
  },
  methods: {
    getGenre(selected) {
      this.selectedGenre = selected;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
