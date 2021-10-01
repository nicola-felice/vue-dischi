<template>

  <section>
    <ul id="albums_container">
      <AlbumCover v-for="(elm, index) in albumsData" :key="index" :album-data="elm" />
    </ul>
  </section>

</template>

<script>
import axios from 'axios';
import AlbumCover from './AlbumCover.vue';

export default {
  name: 'AlbumsSection',
  components: {
    AlbumCover
  },
  data() {
    return {
      albumsData: [],
    }
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then( res => {
        this.albumsData = res.data.response;
      });
  }
}
</script>

<style lang="scss" scoped>
  #albums_container {
    display: flex;
    flex-wrap: wrap;
    color: white;
    list-style: none;
    padding: 4rem 0;
  }
</style>
