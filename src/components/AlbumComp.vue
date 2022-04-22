<template>
  <div class="m-3  bg_custom text-center py-3">
    <img :src="elem.poster" alt="" class="p-2">
    <h3> {{elem.title}} </h3>
    <h4> {{elem.author}} </h4>
    <span> {{elem.year}} </span>
  </div>
</template>

<script>

    export default {
    name: 'AlbumComp',
        props:{
            elem: String,
        // poster: String,
        // title: String,  
        // author: String,
        // year: String,
        // genre: String,
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