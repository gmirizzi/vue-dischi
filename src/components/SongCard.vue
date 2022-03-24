<template>
  <div class="col">
    <div class="card text-center">
      <img
        :src="song.poster"
        class="card-img-top p-3"
        :alt="`poster ` + song.title"
      />
      <div class="card-body">
        <h5 class="card-title text-uppercase text-white">{{ song.title }}</h5>
        <div class="text-secondary">{{ song.author }}</div>
        <div class="text-secondary">{{ song.year }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SongCard",
  props: {
    song: Object,
  },
};
</script>

<style lang="scss" scoped>
.card {
  height: 100%;
  background-color: #2e3a46ff;
}
</style>
