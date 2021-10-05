<template>
  <section>
    <ul id="albums_container">
      <AlbumCover class="album" v-for="(elm, index) in filteredAlbums" :key="index" :album-data="elm" />
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
  props:['musicGenre', 'searchNameAuthor'],
  data() {
    return {
      albumsData: [],
      arrGnres: [],
    }
  },
  computed: {
    filteredAlbums() {
      return this.albumsData.filter( elm => {
        let author = elm.author.toLowerCase();        

        // return the album only if the album genre is selected 
        // or if no genre is selected
        if ( this.musicGenre == "" || elm.genre == this.musicGenre) {
          // and only if in the author search (string) is included the author of the album
          if ( author.includes(this.searchNameAuthor.toLowerCase()) ) {
            return true;
          }
        }
        
        return false;
      });
    },
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then( res => {
        this.albumsData = res.data.response;

        // detect and save the different genres of music from the database
        this.albumsData.forEach( elm => {
          if ( !this.arrGnres.includes(elm.genre) ) {
            this.arrGnres.push(elm.genre);
          }
        });
        this.$emit('genresList', this.arrGnres);
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

  .album {
    width: calc(20% - 1rem);

    @media screen and (max-width: 870px) {
      & {
        width: calc(25% - 1rem);
      }
    } 

    @media screen and (max-width: 600px) {
      & {
        width: calc((100% / 3) - 1rem);
      }
    }

    @media screen and (max-width: 500px) {
      & {
        width: calc((100% / 2) - 1rem);
      }
    }
  }
</style>
