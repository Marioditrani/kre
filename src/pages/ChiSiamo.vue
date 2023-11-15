<script >
  import {state} from '../state.js'
  import sh from '../components/SHeader.vue'

  export default {
    components:{sh},

    data(){
        return{     
            state,
        }
    },
    created(){
   
      this.state.actvPage = 3;
    }
    
  }
</script>

<template>
  <div class="about">
    
    <div class="main-about">
      <div class="top-about">
        <img src="src/assets/img/cuoco-sushi 1.png" alt="">
        <h1>Chi <br> siamo?</h1>
      </div>
      <div class="post-container">
        <div class="post">
          
          <div class="text">
            <h4>LA NOSTRA STORIA...</h4>
            <p>
              Qui, dal marzo del 2017, si servono pizze soffici, gustose e croccanti, preparate con impasti naturali a lunga lievitazione, apprezzati per la leggerezza e la facile digeribilità.
            </p>
          </div>
          <img src="../assets/img/abus.png" alt="">
        </div>
        <div class="post">
          
          <div class="text">
            <h4>LA NOSTRA STORIA...</h4>
            <p>
              Il Capriccio di Leo è una pizzeria a conduzione familiare con un’ampia sala e servizio d’asporto. Punto di forza del locale è la sua pizza ad alta digeribilità cotta nel forno a pietra, con pasta sottile e preparata con un impasto a lunga lievitazione. 
            </p>
          </div>
          <img src="../assets/img/abus.png" alt="">
        </div>
        
        
      </div>
      <Appfooter />
    </div>
</div>

   


</template>

<style scoped lang="scss">
@use '../assets/styles/general.scss' as *;

.btn-menu{
  display: none;
  
  text-transform: uppercase;
  background-color: $c-footer-nav;
  color: $c-nav-link;
  font-weight: bolder;
  width: fit-content;
  padding: 1rem 1rem;
  border-radius: 0 0 20px 20px ;
  
  position: absolute;
  left: 10px;
  top: 0px;

}
@media (max-width:$bp1) {.btn-menu{display:block;}}
.main-about::-webkit-scrollbar{
  width: 10px;
}
.main-about::-webkit-scrollbar-thumb {
  border-radius: 20px;
  background: $c-header;
}
.main-about::-webkit-scrollbar-thumb:hover {
  border-radius: 20px;
  background-color: $c-nav-link;
  border: 2px solid $c-header;
    
}

.about{
  background-color: #270000;
  overflow: hidden;
  display: flex;
  flex-direction:column;
  position: fixed;
  bottom: 0;
  left: 0;
  height: 69%;
  width: 100%;
  .main-about{
    margin:auto;
    width: 70%;
    overflow: auto;
    padding: 2rem;
    height: 100%;

    .top-about{
      display: flex;
      h1{
        font-size: 100px;
        width: 100%;
        text-align: center;
      }
    }
    .post-container{
      margin-top: 2rem;
      display: flex;
      flex-direction: column;
      gap: 2rem;
      .post::after{
        content: ' ';
        display: block;
        background-color: rgba(16, 16, 16, 0.832);
        position: absolute;
        height: 100%;
        width: 100%;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 2;
    
      }
      .post:nth-child(even){
        flex-direction: row-reverse;
      }
      .p2{
        background-image: url(../assets/img/farine.png) !important;
      }
      .post{
        background-image: url(../assets/img/abus.png);
        @include dfc;
        z-index: 1;
        gap: 2rem;
        padding: 2rem;
        background-position: top;
        background-size: cover;
        position: relative;
        .text{
          
          position: relative;
          z-index: 3;
          display: flex;
          flex-direction: column;
          gap: .5rem;
          width: 30%;
          h4{
            font-size: 18px;
          }
          p{
            font-size: 10px;
          }
        }
        img{
          position: relative;
          z-index: 3;
          width: 43%;
          box-shadow: 17px 10px 38px black;
        }
      }
    }
  }
}


@media (max-width:$bp3){
  .post{
    display: flex;
    flex-direction: column !important;
    img{
      width: 70% !important;
    }
    .text{
      width: 70% !important;
    }
  }
}


</style>