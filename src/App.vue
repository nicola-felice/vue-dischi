<template>
  <div id="app">
    <Header @genre="musicGenreSelected" @authorSearch="searchNameAuthor" :arrGenres="genresList" />

    <main>
      <div class="container_medium">
        <AlbumsSection @genresList="generateGenreList" :searchNameAuthor="authorSearch" :musicGenre="musicGenre"/>
      </div>
    </main>

  </div>
</template>


<script>
// components
import Header from './components/Header.vue';
import AlbumsSection from './components/AlbumsSection.vue';
export default {
  name: 'App',
  components: {
    Header,
    AlbumsSection,
  },
  data() {
    return {
      musicGenre: "",
      authorSearch: "",
      genresList: "",
    }
  },
  methods: {
    musicGenreSelected(genre) {
      this.musicGenre = genre;
    },
    searchNameAuthor(authorSearch) {
      this.authorSearch = authorSearch;
    },
    generateGenreList(genresList) {
      this.genresList = genresList;
    }
  }
}
</script>


<style lang="scss">
@import './assets/common.scss';

</style>