<template>
  <main class="py-5">
    <div class="container">
      <div v-if="songs == null" class="text-white text-center">
        LOADING DATA
      </div>
      <div v-else class="row row-cols-5 gy-3">
        <SongCard v-for="el in filter" :key="el.poster" :song="el" />
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
  props: {
    selectedFilter: String,
  },
  computed: {
    filter() {
      if (this.selectedFilter == "") {
        return this.songs;
      } else {
        return this.songs.filter(
          (song) =>
            song.genre.toLowerCase() == this.selectedFilter ||
            song.author.toLowerCase() == this.selectedFilter
        );
      }
    },
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.songs = response.data.response;
      })
      .then(() => this.$emit("populeSelect", this.songs));
  },
};
</script>

<style lang="scss" scoped></style>
