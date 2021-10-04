<template>
  <header>
    <img src="../assets/spotify-logo.png" alt="logo spotify">
    <select @change="$emit('genre', musicGenreSelected)" v-model="musicGenreSelected" name="genreMusic" id="genreMusic">
      <option value="">-select a genre-</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      musicGenreSelected: "",
    }
  }
}
</script>

<style lang="scss" scoped>
  header {
    padding: .75rem 1rem;
    background-color: #2E3A46;

    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  img {
    width: 3.5rem;
  }

  select {
    padding: .25rem;
  }
</style>