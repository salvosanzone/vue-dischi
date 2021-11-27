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
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: calc(100vh - 50px);
    background-color: #1E2D3B;
    .container{
      display: flex;
      flex-direction: column;
      justify-content: center;
      width: 65%;
    }
  }
</style>