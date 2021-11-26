<template>
  <div class="col-ss p-3 text-center">
      <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
      <h6 class="title mt-2">New Jersey</h6>
      <p class="author m-0">Bon Jovi</p>
      <p class="year m-0">1988</p>
  </div>
</template>

<script>
export default {
  name:'Album'
}
</script>

<style lang="scss" scoped>
  .col-ss{
    width: calc(100% / 5 - 20px);
    margin: 10px;
    height: 230px;
    background-color: #2E3A46;
    .title{
      font-size: 15px;
      font-weight: bold;
      text-transform: uppercase;
    }
    .author,
    .year{
      font-size: 11px;
      color: #6F6A66;
    }
  }
</style>