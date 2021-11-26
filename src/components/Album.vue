<template>
  <div class="col-ss p-3 text-center">
      <img :src="album.poster" :alt="album.title">
      <h6 class="title mt-2">{{album.title}}</h6>
      <p class="author m-0">{{album.author}}</p>
      <p class="year m-0">{{album.year}}</p>
  </div>
</template>

<script>
export default {
  name:'Album',
  props:{
    album: Object
  }
}
</script>

<style lang="scss" scoped>
  .col-ss{
    width: calc(100% / 5 - 20px);
    margin: 10px;
    height: 230px;
    background-color: #2E3A46;
    .title{
      font-size: 15px;
      font-weight: bold;
      text-transform: uppercase;
    }
    .author,
    .year{
      font-size: 11px;
      color: #6F6A66;
    }
  }
</style>