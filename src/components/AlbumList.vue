<template>
  <div>
    <Select @selectCategory="performSelect"/>
    <div v-if="loaded" class="row">
    <Album 
    v-for="album in filteredAlbums"
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
import Select from './Select.vue';

export default {
  name:'AlbumList',
  components:{
    Album,
    Loader,
    Select
  },
  data(){
    return{
      albums:[],
      loaded: false,
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      genreToSearch: '' //il parametro che mi arriva dal figlio genere=value lo inserisco all'interno di una variabile
    }
  },
  computed: {
    filteredAlbums(){
      if(this.genreToSearch === ''){
        return this.albums;
      }
      return this.albums.filter( album => {
        return album.genre.includes(this.genreToSearch);
      })
    }
  },

  methods:{

    performSelect(value){
      console.log('performSelect:',value);
      this.genreToSearch = value;

    },


    getApi(){
      //chiamata API
      axios.get(this.apiUrl)
       .then(response  => {
         console.log('response',response);
         this.albums = response.data.response;
         console.log('albums',this.albums);
         this.loaded = true;
       })
       .catch(error => {
         console.log(error);
       })
    },
    
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