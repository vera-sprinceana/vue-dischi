<template>
    <div class="container pt-3">
        <div class="row row-cols-6"> 
            <AlbumComp
                v-for="(element, index) in filterDisk"
                :key="index"
                :elem="element"
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
    props:{
        passaGenProps: String
    },
    computed:{
        filterDisk(){
            if(this.passaGenProps===''){
                return this.dischi
            }else{
                return this.dischi.filter((elem)=>{
                    return elem.genre.includes(this.passaGenProps)
                })
            }
        }
    },
    data(){
        return{
         dischi:[],
         generi:[],
        }
    },
    created(){
        axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
            .then((res)=>{
                console.log( res.data.response );
                this.dischi=res.data.response

                 this.dischi.forEach((elem) => {
                    if(!this.generi.includes(elem.genre))
                    this.generi.push(elem.genre)
                    })
                    this.$emit('generiP', this.generi)
            })
    },     
}

</script>

<style scoped lang="scss">
main{
    color: #fff;
}
 
</style>