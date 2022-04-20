<template>
  <div class="margin_custom col-2 bg_custom">
    <img :src="poster" alt="">
    <h3> {{title}} </h3>
    <p> {{author}} </p>
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
 p{
     color: #fff;
 }
 span{
     color: #fff;
 }
 .bg_custom{
      background-color: #2e3a46;
  }
</style>