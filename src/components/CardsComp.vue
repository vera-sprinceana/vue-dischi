<template>
    <div class="container pt-4">
        <div class="row">
            <AlbumComp
             v-for="(element, index) in diskArray"
             :key="index"
             :author="element.author"
             :poster="element.poster"
             :title="element.title"
             :year="element.year"
            />  
        </div>
        
    </div>
</template>
<script>
import axios from 'axios';
import AlbumComp from './AlbumComp.vue';
export default {
  name: 'CardsComp',
   components: {
        AlbumComp,
    }, 
    data(){
        return{
         diskArray:[]
        }
    },
    created(){
        axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
            .then((res)=>{
                console.log( res.data );
                this.diskArray=res.data
            })
            .catch( (error) => {
                console.log( error )
            })
    },     
         
}
</script>

<style scoped lang="scss">
main{
    color: #fff;
}
 
</style>