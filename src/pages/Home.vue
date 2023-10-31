<script >
  import {state} from '../state.js'
  import axios from 'axios';
  import AppHeader from '../components/AppHeader.vue'
  export default {
    components:{ AppHeader },

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
        <AppHeader class="hd" />
        <div class="main-home">
            <div class="btn-menu" @click="state.openside">. . .</div>
            <div class="carousel bg1" v-if="obs == 0" >
                <div class="par par-1"   > <!--v-if="state.setting[0].status"-->
                    <div class="overlay">
                        <div class="t-c">
                            <h2 id="h2par1">La Kresceria</h2>
                            <p>Scopri la qualità unica della nostra crescia marchigiana a cena o assaggia i nostri primi sensazionali a pranzo...</p>
                        </div>
                        <p>Qui troverai il menu completo della nostra Kresceria... <br> Che aspetti? Ti basta un click!</p>
                        <router-link :to="{ name: 'prenota' }"  class="btn" >Prenota asporto</router-link>
                        <div class="carousel-btn">
                            <div class="btn-c" :class="obs == 0 ? 'btn-active' : ''" @click="primaImg"></div>
                            <div class="btn-c" :class="obs == 1 ? 'btn-active' : ''" @click="secondaImg" v-if="state.setting[0].status" ></div>
                            <div class="btn-c" :class="obs == 2 ? 'btn-active' : ''" @click="terzaImg" v-if="state.setting[1].status"></div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="carousel bg2"  v-if="obs == 1 && state.setting[0].status" >
                <div class="par par-2"   > 
                    <div class="overlay">
                        <div class="t-c">
                            <h2 id="h2par1">La Kresceria</h2>
                            <p>Scopri la qualità unica della nostra crescia marchigiana a cena o assaggia i nostri primi sensazionali a pranzo...</p>
                        </div>
                        <p>Qui troverai il menu completo della nostra Kresceria... <br> Che aspetti? Ti basta un click!</p>
                        <router-link :to="{ name: 'prenota' }"  class="btn" >Prenota asporto</router-link>
                        <div class="carousel-btn">
                            <div class="btn-c" :class="obs == 0 ? 'btn-active' : ''" @click="primaImg"></div>
                            <div class="btn-c" :class="obs == 1 ? 'btn-active' : ''" @click="secondaImg" v-if="state.setting[0].status"></div>
                            <div class="btn-c" :class="obs == 2 ? 'btn-active' : ''" @click="terzaImg" v-if="state.setting[1].status"></div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="carousel bg3" v-if="obs == 2 && state.setting[0].status">
                <div class="par par-3" > 
                    <div class="overlay">
                        <div class="t-c">
                            <h2 id="h2par1">La Kresceria</h2>
                            <p>Scopri la qualità unica della nostra crescia marchigiana a cena o assaggia i nostri primi sensazionali a pranzo...</p>
                        </div>
                        <p>Qui troverai il menu completo della nostra Kresceria... <br> Che aspetti? Ti basta un click!</p>
                        <router-link :to="{ name: 'prenota' }" v-if="obs == 2 && state.setting[0].status" class="btn" >Prenota asporto</router-link>
                        <div class="carousel-btn">
                            <div class="btn-c" :class="obs == 0 ? 'btn-active' : ''" @click="primaImg"></div>
                            <div class="btn-c" :class="obs == 1 ? 'btn-active' : ''" @click="secondaImg" v-if="state.setting[0].status" ></div>
                            <div class="btn-c" :class="obs == 2 ? 'btn-active' : ''" @click="terzaImg" v-if="state.setting[1].status"></div>
                        </div>
                    </div>
                </div>
            </div>
            <Appfooter />
        </div>

    </div>

</template>

<style scoped lang="scss">
@use '../assets/styles/general.scss' as *;



.carousel.bg1{
    background-image: url("https://www.ristorantequadrifogliogradara.it/wp-content/uploads/2020/03/crescia-1080x675.jpg");
    background-size: cover;
}
.carousel.bg2{
    background-image: url("https://i0.wp.com/www.giacomocusano.com/wp-content/uploads/2016/07/coastal-wash-web.jpg?fit=1024%2C682&ssl=1");
    background-size: cover;
}
.carousel.bg3{
    background-image: url("https://www.ristorantequadrifogliogradara.it/wp-content/uploads/2020/03/crescia-1080x675.jpg");
    background-size: cover;
}


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
.hd{box-shadow: 10px 10px 10px black; }
.home{
    overflow: hidden;
    height: 100%;

    .main-home{
        height: 96%;
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
            border-radius: 0 0 20px 20px ;
            
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
                position: absolute;
                top: 0;
                bottom: 0;
                right: 0;
                left: 0;
                padding: 2rem;
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
    width: 100%;
    position: fixed;
    bottom: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    p{
        color: gray;
    }
    
}

@media (max-width:$bp1) {
    .home{
        padding: 0 !important;
        .main-home{
            .par{
                .overlay{
                    row-gap: 3rem;
                    p{
                        font-size: 20px;
                        max-width: 100%;
                        text-align: center;
                    }
                    .t-c{
                        padding-bottom: 1rem;
                        max-width: 100%;

                        p{
                            font-size: 25px;
                        }
                    }
                }
            }
        }
    }
    .main-home{
        padding: 0 !important;
        margin: 0!important;
        width: 100%!important;
    }
    .overlay{
        flex-direction: column!important;
    }
    
    #h2par1, #h2par2, #h2par3
    {
        font-size: 28px;
    }
    
    
}
@media (max-width:$bp1) {.btn-menu{display:block !important;}}

</style>
