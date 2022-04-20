<template>
  <div>
    <HeaderComp/>
    <div class="bg-main">
      <CardsComp/>
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
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
.bg-main{
  background-color: #1e2d3b;
}
</style>
