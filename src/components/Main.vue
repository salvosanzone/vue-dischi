<template>
  <main class="py-5">
    <div class="container">
      <AlbumList />
    </div>
  </main>
</template>

<script>

import AlbumList from './AlbumList.vue';

export default {
  name: 'Main',
  components: {
    AlbumList
  }
}
</script>

<style lang="scss">
  main{
    height: calc(100vh - 50px);
    background-color: #1E2D3B;
    .container{
      width: 60%;
    }
  }
</style>