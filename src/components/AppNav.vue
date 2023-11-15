
<script >
  import {state} from '../state.js';

 export default{
  data(){
    return{
      state,
      infomenu: 0,
    }
  },
  methods: {
    infoside() {
        if (this.infomenu) {
            this.infomenu = 0
        } else {
            this.infomenu = 1
        }
        },
    }
 }
</script>


<template>
  <div class="nav">
    <div class="left-nav">
      <img src="src/assets/img/logo_kojo.jpg" alt="">
    </div>
<<<<<<< HEAD
    <div class="triangolo">
      <div class="triangolo-right">
=======
    
  </div>
  
  <div :class="state.sideMenuValue ? 'nav-mb-on' : 'nav-mb-off'">
    <div :class="state.sideMenuValue ? 'burger-close-on' : 'burger-close-off'" @click="state.openside">
      <div class="line"  :class="state.infomenu ?   'menu-off': 'active-link' "></div>
      <div class="line l1" :class="state.infomenu ?   'menu-off': 'active-link' "></div>
    </div>
    <div :class="state.sideMenuValue ? 'top-on' : 'top-off'">
      <router-link :to="{ name: 'home' }" :class="state.infomenu ?   'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(1)" >home</router-link>
      <router-link :to="{ name: 'menu' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(2)" >menu</router-link>
      <router-link :to="{ name: 'chi-siamo' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(3)" >chi siamo?</router-link>
      <router-link :to="{ name: 'contatti' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(4)" >contatti</router-link>
      <router-link :to="{ name: 'prenota' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(5)" >Ordina d'Asporto</router-link>
      <router-link :to="{ name: 'prenotaServizio' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(6)" >Prenota tavolo</router-link>
      <router-link :to="{ name: 'conferma' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(6)" >conferma</router-link>
      <div class="nav-link info"  :class="state.infomenu ? 'infoopen' : 'infoclose'">
        <div class="top-info">
          <div class="info-n" @click="state.infoside" :class="state.infomenu ? 'info-on' : 'info-n'">infoa</div>
          <div class="info-n" @click="state.infoside" :class="state.infomenu ? 'info-btn' : 'info-n'">+</div>
        </div>
        <div class="infosideopen" :class="state.infomenu ? 'infosideopen' : 'infosideclose'">
          <div class="topinfo" :class="state.infomenu ? 'topinfoopen' : 'topinfoclose'">
            <div class="sec-1">
              <h4>Dove puoi trovarci</h4>
              <p>Borghetto | via borghetto 69</p>
            </div>
            <div class="sec-2">
                <h4>Orari d'apertura</h4>
                <div class="cont-giorni">
                  <span>lunedì</span>
                  <span>martedì</span>
                  <span>giovedì</span>
                  <span>venerdì</span>
                  <span>sabato</span>
                  <span>domenica</span>
              </div>
              <div class="cont-orari">
                <span class="time" >chiusi</span>         
                <span class="time" >16:00 - 22:00</span>
                <span class="time" >16:00 - 22:00</span>
                <span class="time" >16:00 - 22:00</span>
                <span class="time" >16:00 - 22:00</span>
                <span class="time" >16:00 - 22:00</span>
              </div>
            </div>
            <div class="sec-3">
              Capriccio di leo S.r.l, PI: 1231231231231, privacy policy, product by FUTURE+
            </div>
          </div>
        </div>
      </div>
    </div>
    <div :class="state.sideMenuValue ? 'bottom-footer-on' : 'bottom-footer-off'">
      <div class="sec-1">
        <h4>Dove puoi trovarci</h4>
        <p>Borghetto | via borghetto 69</p>
      </div>
      <div class="sec-2">
        <h4>Orari d'apertura</h4>
        <div class="cont-giorni">
          <span>lunedì</span>
          <span>martedì</span>
          <span>giovedì</span>
          <span>venerdì</span>
          <span>sabato</span>
          <span>domenica</span>
        </div>
        <div class="cont-orari">
          <span class="time" >chiusi</span>         
          <span class="time" >16:00 - 22:00</span>
          <span class="time" >16:00 - 22:00</span>
          <span class="time" >16:00 - 22:00</span>
          <span class="time" >16:00 - 22:00</span>
          <span class="time" >16:00 - 22:00</span>
        </div>
>>>>>>> 53b47ff8295b312d6512847b0a1791fb05eaba58

      </div>
    </div>
    <div class="right-nav">
      <div class="main-nav">
        <div class="bg-nav">
          <router-link :to="{ name: 'home' }" :class="state.actvPage == 1 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(1)" >home</router-link>
          <router-link :to="{ name: 'menu' }" :class="state.actvPage == 2 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(2)" >menu</router-link>
          <router-link :to="{ name: 'prenota' }" :class="state.actvPage == 5 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(5)" >Ordina d'Asporto</router-link>
          <router-link :to="{ name: 'prenotaServizio' }" :class="state.actvPage == 6 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(6)" >Prenota tavolo</router-link>
        </div>
        <div class="bottom-nav">
          <router-link :to="{ name: 'chi-siamo' }" class="chi-siamo" ><span>Chi siamo?</span></router-link>
          <router-link :to="{ name: 'contatti' }" class="contatti" > <span>Contatti</span></router-link>
        </div>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@use '../assets/styles/general.scss' as *;
.nav{
  width: 100%;
  height: 100%;
  display: flex;

  .left-nav{
    min-width: 30%;
    display: flex;
    justify-content: center;
  }
  .triangolo{
    width:0;
    border-left: 0px solid transparent;
    border-right: 150px solid transparent;
    border-bottom: 300px solid white;
    -moz-transform:rotate(0);
    -webkit-transform:rotate(0);
    -ms-transform:rotate(0);
    -o-transform:rotate(0);
    transform:rotate(0);
    background-color: #523333;
  }

  .right-nav{
    width: 70%;
    background-color: #523333;
    
    .main-nav{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100%;
      .bg-nav{
        background-color: #712A2A;
        display: flex;
        justify-content: space-between;
        width: 100%;
        padding: 25px 150px 25px 45px;
        border: 5px solid white;
        font-size: 20px;
        text-transform: uppercase;
      }

      .bottom-nav{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        
        
        
        .contatti, .chi-siamo{
          background-color: #523333;
          padding: 10px;
          border: 5px solid white;
          
          
        }
        
        
      }
    }
  }
}

@media (max-width:1500px) {
  .nav{
    .right-nav{
      .main-nav{
        .bg-nav{
          padding: 25px 25px 25px 45px;
        }
      }
    }
  }
}
</style>


