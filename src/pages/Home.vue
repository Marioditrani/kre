<script >
  import {state} from '../state.js'
  import axios from 'axios';
  import AppNav from '../components/AppNav.vue'
  
  export default {
    components:{ AppNav },

    data(){
        return{     
            state,
            obs: 0,
        }
    },
    created(){
        axios.get(state.baseUrl + 'api/setting', {}).then(response=> this.state.setting = response.data.results );
   
        this.state.actvPage = 1;
    },
    methods:{
        primaImg(){
            this.obs = 0
        },
        secondaImg(){
             this.obs = 1
        },
        terzaImg(){
             this.obs = 2
        },
    }


  }
</script>

<template>
    <div class="home">
       <div class="home-left">
            <img src="src/assets/img/sushi.png" alt="" class="sushi">
            <img src="src/assets/img/crop.png" alt="" class="bac">
        </div>
       <div class="home-right">
           <h1>SCOPRI LA VERA CUCINA ORIENTALE E PROVA IL NOSTRO SUSHI</h1>
           <p>SOLO SUL NOSTRO SITO UFFICILAE PUOI TROVARE IL NOSTRO MENU, PERNOTARE UN TAVOLA O ADDIRITTURARA PRENOTARE IL TUO ASPORTO</p>
           <router-link :to="{ name: 'menu' }"  class="btn" >Menu</router-link>

       </div>
        

    </div>

</template>

<style scoped lang="scss">
@use '../assets/styles/general.scss' as *;
*{
    font-family: 'Gabarito', cursive;
}

.main-home::-webkit-scrollbar{
        
        width: 10px;
        height: 10px;
        
    }

.main-home::-webkit-scrollbar-thumb {
    border-radius: 20px;
    background: $c-header;
    
}
.main-home::-webkit-scrollbar-track {
    border-radius: 20px;
    background: rgba(52, 4, 7, 0.786);
    
}
.main-home::-webkit-scrollbar-thumb:hover {
    border-radius: 20px;
    background-color: $c-nav-link;
    border: 2px solid $c-header;
    
}

.home{
<<<<<<< HEAD
    background-color: #270000;
    height: 70%;
=======
    overflow: hidden;
    height:100%;

    .main-home{
        height: 100%;
        //display: flex;
        gap: 3rem;
        border: 5px solid white;

        .btn-menu{
            display: none;
            text-transform: uppercase;
            background-color: black;
            color: white;
            font-weight: bolder;
            width: fit-content;
            padding: .1rem 1rem 1rem;
            border-radius: 0 0 20px 20px;
            position: absolute;
            left: 6px;
            top: 5px;
            z-index: 10;
        }
        
        .carousel{
        height: 100%;
        width: 100%;
        
        
        }
        .par{
            scroll-snap-align: start;
            flex: 1 0 auto;
            height: 100%;
            width: 100%!important;
            color: $c-white;
            //filter: grayscale(50);
            background-position: center bottom;
            background-size: cover;
            position: relative;
            .overlay{
                background: linear-gradient(rgba(0, 0, 0, 0.832), rgba(0, 0, 0, 0.359));
                padding: 2rem;
                height:  100%;
                @include dfc;
                flex-direction: column;
                row-gap: 2rem;
                justify-content: space-between;
                padding-bottom: 10rem;
                .t-c{
                    display: flex;
                    flex-direction: column;
                    gap: 1rem;
                    max-width: 90%;
                    text-align: center;
                    padding-top: 4rem;
                    padding-bottom: 18rem;
                    h2{
                        line-height: 38px;
                        font-size: 70px;
                        font-family: 'Playball', cursive;
                    }
                    
                }
                .carousel-btn{
                    
                    display: flex;
                    gap: 1rem;
                    
                    .btn-c{
                        width:25px;
                        aspect-ratio: 1;
                        border-radius: 50%;
                        background-color: black;
                        
                    }
                    .btn-active{
                        border: 2px solid white;
                    }
                    
                }
                p{
                    font-size: 30px;
                    
                }
                

            }

        }
    }
}
.par-1{
    
    background-position: center !important;
}
.footer{
    height: 4%;
>>>>>>> 53b47ff8295b312d6512847b0a1791fb05eaba58
    width: 100%;
    position: fixed;
    bottom: 0;
    display: flex;

    .home-left{
        
        width: 50%;
        position: relative;
        
        .sushi{
            position: absolute;
            left: 30%;
            top: 25%;
        }
        .bac{
            position: absolute;
            left: 65%;
            top: 30%;
            transform: rotate(-40deg);
        }
        
    }
    .home-right{
        font-size: 25px;
        width: 40%;
        height: 90%;
        padding-top: 70px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        p{
            width: 70%;
            align-self: flex-end;
            font-size: 20px;
        }
        .btn{
            width: 200px;
            padding: 20px 0;
            border-radius: 50px;
            display: flex;
            justify-content: center;
            align-self: center;
            font-size: 25px;
            background-color: #523333;
            border: 5px solid white;
        }
    }
    
}


@media (max-width:1600px) {
  
}


</style>
