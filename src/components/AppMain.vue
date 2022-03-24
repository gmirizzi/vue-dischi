<template>
  <main>
    <div class="container">
      <SongCard />
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
  color: white;
}
</style>
