<template>
  <div class="row">
    <Album 
    v-for="album in albums"
    :key="album.id"

    />
    
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
  data(){
    return{
      albums:[]
    }
  },
  methods:{
    getApi(){
      //faccio la chiamata API
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
       .then(response  => {
         console.log(''response);
         this.albums = response.data;
         console.log('array',this.albums);
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