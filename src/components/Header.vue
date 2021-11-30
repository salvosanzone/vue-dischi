<template>
  <header >
    <i class="logo fab fa-spotify"></i>
    <select
    v-model="value"
    @change="$emit('selectGenre', value)"
  >
    <option value="">Seleziona genere</option>
    <option
      v-for="(genre, index) in genresList"
      :key="index"
      :value="genre">{{genre}}</option>
    
  </select>
  </header>
</template>

<script>
export default {
  name:'Header',
  components:{
  },
  data(){
    return {
      value:''
    }
  },
  methods:{
   
  },
  props:{
    genresList: Array
  }
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';
@import '../assets/style/mixins.scss';

  header{
    @include flex('center');
    justify-content: space-between;
    height: 50px;
    padding: 10px;
    background-color: $primary-color;
    .logo{
      line-height: 50px;
      font-size: 35px;
      color: #1DD15E;
    }
    select{
      border: 2px solid #1E2D3B;
      border-radius: 5px;
      padding: 5px 20px;
    }
  }
</style>