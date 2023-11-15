<script >
  
  import AppNav from './components/AppNav.vue'
  import Appfooter from './components/Appfooter.vue'


  export default {
  components:{  AppNav, Appfooter }
  }
</script>

<template>

  <div class="container">
    <AppNav class="appnav"/>
    <router-view class="page"></router-view>
    
  </div>
 

  
</template>

<style lang="scss">
@use './assets/styles/general.scss' as *;



</style>
