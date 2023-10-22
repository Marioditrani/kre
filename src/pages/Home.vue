<script >
  import {state} from '../state.js'
  import axios from 'axios';
  import AppHeader from '../components/AppHeader.vue'
  export default {
    components:{ AppHeader },

    data(){
        return{     
            state,
        }
    },
    created(){
        //axios.get(state.baseUrl + 'api/setting', {}).then(response=> this.state.setting = response.data.results );
   
        this.state.actvPage = 1;
    }

  }
</script>

<template>
    <div class="home">
        <AppHeader class="hd" />
        <div class="main-home">
            
            <div class="par par-1"  v-if="state.setting[0].status">
                <div class="overlay">
                    <div class="t-c">
                        <h2 id="h2par1">La Kresceria</h2>
                        <p>Scopri la qualità unica della nostra crescia marchigiana a cena o assaggia i nostri primi sensazionali a pranzo...</p>
                    </div>
                    <p>Qui troverai il menu completo della nostra Kresceria... <br> Che aspetti? Ti basta un click!</p>
                    <router-link :to="{ name: 'prenota' }" class="btn" >Prenota asporto</router-link>
                </div>
            </div>
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
.hd{box-shadow: 10px 10px 10px black; }
.home{
    position: fixed;
    top: 0;
    right: 0;
    overflow: hidden;
    height: 100%;
    .main-home{
        height: 96%;
        display: flex;
        gap: 3rem;
        border: 5px solid white;
        
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
                justify-content: space-between;
                padding-bottom: 10rem;
                .t-c{
                    display: flex;
                    flex-direction: column;
                    gap: 1rem;
                    max-width: 90%;
                    text-align: center;
                    padding-top: 4rem;
                    padding-bottom: 20rem;
                    h2{
                        line-height: 38px;
                        font-size: 70px;
                        font-family: 'Playball', cursive;
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
    background-image: url("https://www.ristorantequadrifogliogradara.it/wp-content/uploads/2020/03/crescia-1080x675.jpg");
    background-position: center !important;
}

@media (max-width:$bp1) {
    .home{
        padding: 0 !important;
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
@media (max-width:$bp1) {

}
</style>
