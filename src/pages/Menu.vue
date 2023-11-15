<script >
  import {state} from '../state.js';
  import axios from 'axios'
  import sh from '../components/SHeader.vue'
  import AppNav from '../components/AppNav.vue'

  export default {
    components:{AppNav},

    data(){
        return{     
            state,
            arrProduct:[],
            arrCategory:[],
            categoryId: 0,
            actvcat: 1,
        }
    },
    methods:{
      getProduct(cat){
        this.categoryId = cat,
        axios
				.get(state.baseUrl + 'api/projects', {
					params: {
						category: this.categoryId,
					},
				})
				.then(response => {
          this.arrProduct = response.data.results.data;
				});
      },
      getCategory(){

        axios
				.get(state.baseUrl + 'api/categories', {})
				.then(response => {
          this.arrCategory = response.data.results;
				});
 
      },
      changeCategory(value){
        if(value==1){
          this.getProduct(0)
          this.actvcat=value
          
        }else{
          this.getProduct(value)
          this.actvcat=value

        }
      },
      getPrice(cent){
        let num = parseFloat(cent);
        num = num / 100;
        num = "€" + num  
        
        return num
      },
      fixtag(arr){
        let arrtag='';
        arr.forEach((element, i) => {
          
          if(i+1==arr.length){
            
            arrtag = arrtag + element.name + '.'
          }else{
            arrtag = arrtag + element.name + ', '
            
          }
        });
        return arrtag
      },
      
      
      
    },
    created(){
      this.getProduct(0);
      this.getCategory();


      this.state.actvPage = 2;
    },
    
  }
</script>

<template>
  <div class="menu">
    <AppNav class="nav"/>
    <div class="menu-cont">
      <div class="menu-left">
        <img src="src/assets/img/crop.png" alt="" class="bac">
        
      </div>
      <div class="menu-right">
        <div class="menu-top">
          <div class="menu-top-left">
            <h1>Menu</h1>
            <p>Le delizie del nostro menu aspettano solo te...</p>
          </div>
          <div class="menu-top-right">
            <div class="categorie">
              <div v-for="cat in arrCategory" class="category" :class="actvcat == cat.id ? 'category-on' : '' " @click="changeCategory(cat.id)"> 
                <span :class="actvcat == cat.id ? 'span-on' : '' ">{{ cat.name }}</span>
              </div>
            </div>
            
          </div>
        </div>
        <div class="menu-bottom">

          <div class="card" v-for="item in state.fakemenu[0]">
            <div class="title">{{ item.name }}</div>
            <img src="../assets/img/imgsushi.png" alt="">         <!--state.getImageUrl(item.image)-->
            <div class="c-tp">
              <div class="tags"> <span>{{fixtag(item.tags) }}</span></div>
              <div class="price">{{ getPrice(item.price) }}</div>
            </div>
          </div>
          
        </div>

      </div>
    </div>
    
  </div>
  <Appfooter />
</template>

<style scoped lang="scss">
@use '../assets/styles/general.scss' as *;


.menu-cont::-webkit-scrollbar{
      
      width: 10px;
      height: 10px;
      
  }

.menu-cont::-webkit-scrollbar-thumb {
    border-radius: 20px;
    background: $c-header;
    
}
.menu-cont::-webkit-scrollbar-track {
    border-radius: 20px;
    background: rgba(52, 4, 7, 0.786);
    
}
.menu-cont::-webkit-scrollbar-thumb:hover {
    border-radius: 20px;
    background-color: $c-nav-link;
    border: 2px solid $c-header;
    
}
.hd{box-shadow: 10px 10px 10px black; }

.menu{
  width: 100%;
  overflow: hidden;
  height: 70%;
  display: flex;
  flex-direction:column;
  position: fixed;
  top: 0;
  left: 0;
  height: 96%;

  .nav{
    height: 30%;
  }
  .menu-cont{
    display: flex;
    background-color: #270000;
    position: fixed;
    bottom: 0;
    height: 70%;
    width: 100%;
    padding: 1rem 1rem ;

    .menu-left{
      width: 10%;
      display: flex;
      align-items: center;
      position: relative;
      
      .bac{
        width: 100%;
        margin: auto;
      }
      
    }

    .menu-right{
      width: 90%;
      .menu-top{
        height: 30%;
        display: flex;
        justify-content: space-between;
        h1{
          text-transform: uppercase;
          font-size: 80px;
          padding-top: 2rem;
        }
        p{
          font-size: 25px;
         
        }
      }
      .menu-bottom{
      height: 72%;
      overflow: auto;
      @include dfc;
      flex-wrap: wrap;
      gap: 1rem;
      align-items: stretch;
      .card{
        border-radius: 10px;
        width: calc((75% - 2rem) / 3);
        padding: 10px;
        position: relative;
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin: 15rem 1rem;
        margin-bottom:0 ;
        
        
        
        img{
          position: absolute;
          top: -175px;
          left: 0;
          right: 0;
          margin: auto;
          width: 300px;
          
          
        }
        .title{
          font-size: 20px;
          width: 100% ;
          text-transform: upercase;
          position: absolute;
          left:40px;
          top:20px;
          z-index: 10001;
        }
        .c-tp{
          background-color: #AB2F2F;
;
          position: relative;
          z-index: 10000;
          width: 100%;
          height: 100%;
          display: flex;
          flex-direction: column;
          padding: 2rem;
          border-radius: 20px;
          justify-content: space-between;
          
          
          
          .tags, .price{
            border-radius: 10px;
            width: 100%;
            padding-right: .5rem;
            padding-bottom: .5rem;
          }
          .tags{

            display: flex;
            padding-top: 1rem;
            padding-right: .5rem;
            span{
              font-size: 13px;
              font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
              font-weight: bold!important; 


            }
          }
          .price{
            width: 100%;
            //border-radius: 10px ;
            text-align: right;
  
          }
        }
      }
      }
    }
    
    
    .main-menu{
      

    }
    
  }


}

/*** */

.categorie {
  max-width: 450px;
  width: 100%;
  height: 160px;
  border-radius: 4px;
  display: flex;
  gap: 5px;
  padding: .4em;
  margin: 0 auto;
  .category {
   height: 100%;
   flex: 1;
   overflow: hidden;
   cursor:grab;
   border-radius: 2px;
   transition: all .5s;
   background-color: $c-footer-nav ;
   border: 1px solid $c-nav-link;
   display: flex;
   justify-content: center;
   align-items: center;
   span {
    min-width: 14em;
    padding: .5em;
    text-align: center;
    transform: rotate(-90deg);
    transition: all .5s;
    text-transform: uppercase;
    color: $c-nav-link;
    letter-spacing: .1em;
   }
  }
  .category:hover {
    flex: 5;
    background-color: $c-header !important;
  }
  .category:hover span {
    color: white;
   transform: rotate(0);
  }
}

.category-on {
  flex: 2!important;
  background-color: $c-header !important;
}
.category-on:hover {
  flex: 5!important;
  background-color: $c-header !important;
}
.span-on{
  color: white!important;;

}


/***** */


@media (max-width:$bp2) {
  .card{
    width: 95% !important;
  }
}
@media (max-width:$bp1) {
  .menu{
    width:100%;
  }
}
</style>
