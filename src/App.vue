<script >
  
  import AppNav from './components/AppNav.vue'
  import Appfooter from './components/Appfooter.vue'


  export default {
  components:{  AppNav, Appfooter }
  }
</script>

<template>

  <div class="container">
    <AppNav />
    <router-view class="page"></router-view>
    <Appfooter />
  </div>
 

  
</template>

<style lang="scss">
@use './assets/styles/general.scss' as *;
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


@media (max-width:$bp1) {
  .page{
    width: 100%!important;
  }
  
}

body::-webkit-scrollbar{
  width: 10px;
}
body::-webkit-scrollbar-thumb {
  border-radius: 20px;
  background: $c-header;
}
body::-webkit-scrollbar-thumb:hover {
  border-radius: 20px;
  background-color: $c-nav-link;
  border: 2px solid $c-header;
    
}

</style>
