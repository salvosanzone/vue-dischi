<template>
  <div>
    <div v-if="loaded" class="row">
    <Album 
    v-for="album in filteredAlbums"
    :key="album.id"
    :albumData="album" 
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
    Loader,
  },
  props:{
    selectValue: String
  },
  data(){
    return{
      albums:[],
      loaded: false,
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      genres:[]
    }
  },
  computed: {
    //il filter genera un array,filter fa il push dentro l'array di 'album' quando la condizione 'album.genre....' è vera. Dunque filteredAlbums è un array composta solo dal frutto del filtro
    //selectValue = genreToSearch
    filteredAlbums(){
      if(this.selectValue === ''){
        return this.albums;
      }
      return this.albums.filter( album => {
        return album.genre === (this.selectValue);
      })
    }
  },

  methods:{

    getApi(){
      //chiamata API
      axios.get(this.apiUrl)
       .then(response  => {
         this.albums = response.data.response;

         this.albums.forEach(album => {
           if(!this.genres.includes(album.genre)){
             this.genres.push(album.genre);
           }
         });
          this.$emit('genresList', this.genres);
          console.log('Partenza $emit genresList da AlbumList -> Main.vue');

         
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