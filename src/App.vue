<script>
import NavComponent from './components/NavComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
  export default{
    components:{
    NavComponent,
    MainComponent,
    FooterComponent
    }
  }

</script>


<template>
  <NavComponent/>
  <MainComponent/>
  <FooterComponent/>
</template>

<style lang="scss">
  @use'./style/general'
</style>
