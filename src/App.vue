<template>
  <div>
    <HeaderComp
    :passaGeneriProps="generi"
    @inviaGenSel="ottieniGenSel"
    />
    <div class="bg-main">
      <CardsComp
      @generiP="ottieniGeneri"
      :passaGenProps="genereSelezionato"
      />
    </div>
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'
import CardsComp from './components/CardsComp.vue'
export default {
  name: 'App',
  components: {
    HeaderComp,
    CardsComp,
  },
  data(){
    return{
      generi:[],
      genereSelezionato:''
    }
    
  },
  methods:{
    ottieniGeneri(myGenre){
      this.generi=myGenre
    },
    ottieniGenSel(genSel){
      this.genereSelezionato=genSel
    }
  }
}
</script>
<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
.bg-main{
  background-color: #1e2d3b;
}
</style>
