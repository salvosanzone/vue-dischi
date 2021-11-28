<template>
  <header>
    <i class="logo fab fa-spotify"></i>
  </header>
</template>

<script>
export default {
  name:'Header',
  
}
</script>

<style lang="scss">
@import '../assets/style/vars.scss';

  header{
    height: 50px;
    background-color: $primary-color;
    .logo{
      line-height: 50px;
      margin-left: 10px;
      font-size: 35px;
      color: #1DD15E;
    }
  }
</style>