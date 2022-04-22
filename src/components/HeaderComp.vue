<template>
  <header class="d-flex justify-content-between align-items-center">
    <img src="../assets/img/spotify-logo.png" alt="" class="m-3">
    <div>
      <label for="" class="d-flex text-white">Seleziona il genere</label>
      <select 
      class="p-2 me-3"
      v-model="selected"
      @change="$emit('inviaGenSel', selected)"
      >
        <option selected>Tutti i generi</option>
        <option v-for="(elem, index) in passaGeneriProps"
        :key="index"
        :value="elem"> 
        {{elem}} </option>
      </select>
    </div>
    
  </header>
</template>

<script>
import "bootstrap"
export default {
  name: 'HeaderComp',
  props: {
    passaGeneriProps : Array
  },
  data(){
    return{
      selected:''
    }
  }
}
</script>

<style lang="scss">
header{
  background-color: #2e3a46;
  height: 100px;
}
img{
  width: 50px;
}
</style>
