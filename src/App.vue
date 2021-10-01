<template>
  <div id="app">
    <Header/>

    <main>
      <div class="container_medium">
        <AlbumsSection/>
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
    AlbumsSection
  }
}
</script>


<style lang="scss">
@import './assets/common.scss';

</style>
