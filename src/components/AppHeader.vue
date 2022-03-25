<template>
  <header class="d-flex justify-content-between align-items-center p-2">
    <img src="./../assets/img/logo-spotify.png" alt="Logo Spotify" />
    <select @change="$emit('filtra', selected)" v-model="selected">
      <option value="">Seleziona un genere</option>
      <option
        v-for="(el, index) in genres"
        :key="index"
        :value="el.toLowerCase()"
      >
        {{ el }}
      </option>
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
