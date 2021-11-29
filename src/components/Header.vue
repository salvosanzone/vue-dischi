<template>
  <header @selectCategory="">
    <i class="logo fab fa-spotify"></i>
    <Select />
  </header>
</template>

<script>
export default {
  name:'Header',
  components:{
    Select
  }
}
import Select from './Select.vue';
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
  }
</style>