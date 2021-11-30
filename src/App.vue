<template>
 <div>
   <Header @selectGenre="performSelect"/>
   <Main :generateSelected="genreToSearch" />
 </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
   Header,
   Main,
  },
  data(){
    return{
      genreToSearch: '' //il parametro che mi arriva dal figlio genere=value lo inserisco all'interno di una variabile in modo tale da salvarlo,alla fine lui lo ritrovo nella props di albumList col nome di selectValue
    };
  },
  methods: {
    //con questa funzione vado a salvare in una mia variabile il parametro che avevo passato dietro le quinte ossia value,avrei potuto scrivere anche value qui, genere = value
    performSelect(genere){
      console.log('performSelect:',genere);
      this.genreToSearch = genere;

    }
  },
}
</script>

<style lang="scss">
@import './assets/style/vars.scss';
@import './assets/style/general.scss';
</style>
