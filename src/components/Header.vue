<template>
  <header>
    <i class="logo fab fa-spotify"></i>
  </header>
</template>

<script>
export default {
  name:'Header'
}
</script>

<style lang="scss">
  header{
    height: 50px;
    background-color: #2E3A46;
    .logo{
      line-height: 50px;
      margin-left: 10px;
      font-size: 35px;
      color: #1DD15E;
    }
  }
</style>