
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
    <p>La Kresceria 123123123 │ privacy policy │ credit │ powered by future + </p>
</div>
</template>

<style lang="scss" scoped>
@use '../assets/styles/general.scss' as *;
.footer{
  padding: .7rem;
  text-align: center;
  width: 100%;



  p{
    color: grey;
  }
}
@media (max-width:$bp1) {
    p{
      font-size: 10px;
      padding: 3px;
    }
  }
</style>
