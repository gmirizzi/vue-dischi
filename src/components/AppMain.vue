<template>
  <main>
    <div class="container">
      <SongCard />
    </div>
  </main>
</template>

<script>
import SongCard from "./../components/SongCard.vue";

export default {
  name: "AppMain",
  components: {
    SongCard,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: #1e2d3bff;
  color: white;
}
</style>
