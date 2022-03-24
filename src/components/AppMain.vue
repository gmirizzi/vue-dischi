<template>
  <main class="py-5">
    <div class="container">
      <div v-if="songs == null" class="text-white text-center">
        LOADING DATA
      </div>
      <div v-else class="row row-cols-5 gy-3">
        <SongCard v-for="el in songs" :key="el.poster" :song="el" />
      </div>
    </div>
  </main>
</template>

<script>
import SongCard from "./../components/SongCard.vue";
import axios from "axios";

export default {
  name: "AppMain",
  data() {
    return {
      songs: null,
    };
  },
  components: {
    SongCard,
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.songs = response.data.response;
        console.log(this.songs);
      });
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: #1e2d3bff;
}
</style>
