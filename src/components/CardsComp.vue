<template>
    <div class="container pt-3">
        <div class="row row-cols-6"> 
            <div class="d-flex">
                <SelectComp @funzioneSelezione="metodoSelezione"/> 
            </div>
           
            <AlbumComp
                v-for="(element, index) in filtraggioSelezione"
                :key="index"
                :author="element.author"
                :poster="element.poster"
                :title="element.title"
                :year="element.year"
                :genre="element.genre"
            /> 
               
        </div>
           
    </div>
</template>
<script>
import axios from 'axios';
import AlbumComp from './AlbumComp.vue';
import SelectComp from './SelectComp.vue';
export default {
  name: 'CardsComp',
   components: {
        AlbumComp,
        SelectComp,
    }, 
    data(){
        return{
         filtraggioArray:[],
         testoRicerca: '',
        }
    },
    conputed:{
        filtraggioSelezione(){
            if( this.testoRicerca === '' ){
            return this.filtraggioArray
            }
            return this.filtraggioArray.filter( (elem) => {
            return elem.genre.toLowerCase().includes(this.testoRicerca.toLowerCase())
        })
      
        
    },
    created(){
        axios.get( 'https://flynn.boolean.careers/exercises/api/array/music' )
            .then((res)=>{
                console.log( res.data.response );
                this.filtraggioArray=res.data.response
            })
            .catch( (error) => {
                console.log( error )
            })
    },  
    methods:{
        metodoSelezione(testo){
            console.log(testo)
            this.testoRicerca = testo
            console.log(this.testoRicerca)
        },
    },
   
         
}


}
</script>

<style scoped lang="scss">
main{
    color: #fff;
}
 
</style>