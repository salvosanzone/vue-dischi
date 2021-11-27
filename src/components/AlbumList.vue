<template>
  <div>
    <div v-if="loaded" class="row">
    <Album 
    v-for="album in albums"
    :key="album.id"
    :album="album" 
    />
    </div >
    <Loader v-else/>
  </div>
  
</template>

<script>
import axios from 'axios';
import Album from './Album.vue';
import Loader from './Loader.vue';

export default {
  name:'AlbumList',
  components:{
    Album,
    Loader
  },
  data(){
    return{
      albums:[],
      loaded: false
    }
  },
  methods:{
    getApi(){
      //chiamata API
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
       .then(response  => {
         console.log('response',response);
         this.albums = response.data.response;
         console.log('albums',this.albums);
         //this.loaded = true;
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

<style lang=scss>
 .row{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>