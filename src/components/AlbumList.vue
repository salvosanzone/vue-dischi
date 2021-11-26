<template>
  <div class="row">
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
    <Album />
  </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue';

export default {
  name:'AlbumList',
  components:{
    Album
  },
  methods:{
    getApi(){
      //fa la chiamata 
      axios.get('https://flynn.boolean.careers/exercises/api/array/music');
       .then(re  => {
         console.log(response);
       })
       .catch(error => {
         console.log(error);
       })
    }
  },
  mounted(){
    this.getApi()
  }
}
</script>

<style >
 
</style>