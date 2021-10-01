<template>
  <li>
    <img :src="albumData.poster" :alt="albumData.title + 'image'">
    <div class="title_album">{{albumData.title}}</div>
    <div class="author_album">{{albumData.author}}</div>
    <div class="year_album">{{albumData.year}}</div>
  </li>
</template>

<script>
export default {
  name: 'Album',
  props: ['albumData']
}
</script>

<style lang="scss" scoped>
  li {
    width: calc(20% - 1rem);
    background-color: #2E3A46;
    text-align: center;
    padding: 1rem;
    margin: .5rem;

    img {
      margin-bottom: 1rem;
    }

    .title_album {
      text-transform: uppercase;
      font-weight: 800;
      font-size: 1.1rem;
      margin-bottom: .75rem;
    }

    .year_album,
    .author_album {
      color: #808080;
      text-transform: capitalize;
      font-size: .85rem;
      font-weight: 500;
    }
    .year_album {
      margin-bottom: .25rem;
      margin-top: .15rem;
    }
  }
</style>