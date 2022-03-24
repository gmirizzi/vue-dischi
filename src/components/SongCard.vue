<template>
  <div class="col">
    <div class="card">
      <img
        :src="song.poster"
        class="card-img-top"
        :alt="`poster ` + song.title"
      />
      <div class="card-body">
        <h5 class="card-title">{{ song.title }}</h5>
        <p class="card-text">{{ song.author }}</p>
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

<style></style>
