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
<<<<<<< HEAD
=======
body{
  background-color: $c-bg;
}

.container{
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.page{
    width: 70% !important;
    padding: 0 2rem ;
    overflow: auto;
    position: relative;
    z-index: 10;
  
}
>>>>>>> 53b47ff8295b312d6512847b0a1791fb05eaba58



</style>
