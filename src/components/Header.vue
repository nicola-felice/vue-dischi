<template>
  <header>
    <img src="../assets/spotify-logo.png" alt="logo spotify">

    <input @keyup="$emit('authorSearch', searchNameAuthor)" v-model="searchNameAuthor" type="text" placeholder="cerca nome artista">

    <select @change="$emit('genre', musicGenreSelected)" v-model="musicGenreSelected" name="genreMusic" id="genreMusic">
      <option value="">-seleziona un genere-</option>
      <option v-for="(elm, index) in arrGenres" :key="index" :value="elm">{{elm}}</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      musicGenreSelected: "",
      searchNameAuthor: "",
    }
  },
  props: ['arrGenres']
}
</script>

<style lang="scss" scoped>
  header {
    padding: .75rem 1rem;
    background-color: #2E3A46;

    display: flex;
    align-items: center;
  }

  img {
    width: 3.5rem;
  }

  input {
    margin-left: auto;
    margin-right: 1rem;
  }

  select,
  input {
    padding: .25rem;
  }
</style>