<template>
  <div id="app">
    <Header @genre="musicGenreSelected" />

    <main>
      <div class="container_medium">
        <AlbumsSection :musicGenre="musicGenre"/>
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
    }
  },
  methods: {
    musicGenreSelected(genre) {
      this.musicGenre = genre;
    }
  }
}
</script>


<style lang="scss">
@import './assets/common.scss';

</style>