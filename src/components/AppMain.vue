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
  components: {
    SongCard,
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        console.log(response.data.response);
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
