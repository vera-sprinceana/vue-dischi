<template>
  <div class="m-3  bg_custom text-center py-3">
    <img :src="poster" alt="" class="p-2">
    <h3> {{title}} </h3>
    <h4> {{author}} </h4>
    <span> {{year}} </span>
  </div>
</template>

<script>

    export default {
    name: 'AlbumComp',
    props:{
        poster: String,
        title: String,  
        author: String,
        year: String,
    }
    }
</script>

<style scoped lang="scss">
 .margin_custom{
     margin: 0 10px 10px 0;
 }
 h3{
     color: #fff;
     text-transform: uppercase;
 }
 h4,
 span{
     color: #7b7b7c;
 }
 .bg_custom{
      background-color: #2e3a46;
  }
  img{
      width: 100%;
  }
</style>