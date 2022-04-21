<template>
  <div class="d-flex">
    <select name="" id="" class="w-100"
     v-model.trim="searchText">
      <option 
      value=""
      @click="$emit('funzioneSelezione', searchText)"
      > {{genre}} </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'SelectComp',
  props:{
    genre: String,
    },
    data(){
      return {
        searchText: ''
      }
    }
}
</script>

<style lang="scss">

</style>