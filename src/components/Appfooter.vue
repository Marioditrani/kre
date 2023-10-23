
<script >
  import {state} from '../state.js';

 export default{
  data(){
    return{
      state,
    }
  },
  
 }
</script>


<template>
 <div class="footer">
<p>asfsfa</p>
 </div>
</template>

<style lang="scss" scoped>
@use '../assets/styles/general.scss' as *;
.footer{
  height: 4%;
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 0;

  p{
    color: grey;
  }
}

</style>
