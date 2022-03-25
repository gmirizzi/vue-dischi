<template>
  <header class="d-flex justify-content-between align-items-center p-2">
    <img src="./../assets/img/logo-spotify.png" alt="Logo Spotify" />
    <select @change="$emit('filtra', selected)" v-model="selected">
      <option value="">All</option>
      <optgroup label="Genere">
        <option
          v-for="(el, index) in genres"
          :key="index"
          :value="el.toLowerCase()"
        >
          {{ el }}
        </option>
      </optgroup>
      <optgroup label="Artista">
        <option
          v-for="(el, index) in authors"
          :key="index"
          :value="el.toLowerCase()"
        >
          {{ el }}
        </option>
      </optgroup>
    </select>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      selected: "",
    };
  },
  props: {
    genres: [],
    authors: [],
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: #2e3a46ff;
  img {
    height: 50px;
  }
}
</style>
