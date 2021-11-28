<template>
  <div class="col">
      <img :src="album.poster" :alt="album.title">
      <h6 class="title">{{album.title}}</h6>
      <p class="author m-0">{{album.author}}</p>
      <p class="year m-0">{{album.year}}</p>
  </div>
</template>

<script>
export default {
  name:'Album',
  props:{
    //sul ciclo inseriro questa props
    album: Object
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
  .col{
    width: 145px;
    height: 240px;
    margin: 10px;
    padding: 15px;
    text-align: center;
    box-shadow: 0 10px 10px rgba($color: #000000, $alpha: .5);
    background-color: $primary-color;
    transition: all 0.3s;
    &:hover{
      transform: scale(1.05);
      cursor: pointer;
    }
    .title{
      font-size: 15px;
      margin: 10px 0;
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