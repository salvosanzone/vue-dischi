<template>
  <main @genresList="genresToPops"
  class="py-5"
  >
    <div class="container">
      <AlbumList :selectValue="generateSelected" />
    </div>
  </main>
</template>

<script>

import AlbumList from './AlbumList.vue';

export default {
  name: 'Main',
  components: {
    AlbumList
  },
  props:{
    //genreToSearch = generateSelected
    generateSelected: String
  },
  data(){
    return{
      genresOfMusic:[]
    }
  },
  methods:{
    genresToPops(genres){
      this.genresOfMusic = genres
      this.$emit('genresListOfMusic', this.genresOfMusic)
    }
  }
}
</script>

<style lang="scss">
@import '../assets/style/mixins.scss';
  main{
    @include flex('center');
    min-height: calc(100vh - 50px);
    background-color: #1E2D3B;
    .container{
      @include flex('columb');
      width: 65%;
    }
  }
</style>