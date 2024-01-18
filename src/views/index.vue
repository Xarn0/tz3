<template>
<div class="container">
  <div class="dialog ">
    <div class="dialog__header">
      <div class="dialog__logo">Chagenger</div>
      <div class="dialog__title">Управление транспортом</div>
      <div class="dialog__close">
        <svg width="66" height="66" viewBox="0 0 66 66" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M33.0003 36.8306L47.3351 51.1654L51.1653 47.3352L36.8305 33.0004L51.1652 18.6656L47.3351 14.8355L33.0003 29.1702L18.6653 14.8352L14.8351 18.6654L29.1701 33.0004L14.8351 47.3355L18.6653 51.1656L33.0003 36.8306Z" fill="#F1F1F1"/>
        </svg>
</div>
    </div>
    <div class="dialog__content-main" :class=classContainer >
      <div class="dialog__content" v-if="items.length<=8" >

    
            <div 
            class="dialog__item" 
            :key="index"
            v-for="(item,index) in items">
              <h5 class="dialog__item-title">{{ item.title }}</h5>
              <p class="dialog__item-content">
                
                <!-- <span>$</span> 
                <span>cor</span> 
                <span></span>  -->
                <span class="simpleDollars" v-if="item.element=='simpleDollars'">$</span> 
                <span class="crown" v-else-if="item.element=='crown'">
                  <svg width="44" height="44" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <g opacity="0.4">
                      <path fill-rule="evenodd" clip-rule="evenodd" d="M35.0002 2.91666C36.1821 2.91666 37.2472 3.62993 37.6972 4.72281L46.4072 25.8757L59.4032 15.2426C60.3493 14.4686 61.6777 14.3666 62.7308 14.9871C63.784 15.6077 64.3385 16.8191 64.1198 18.0217L58.3335 49.8463V61.25C58.3335 62.8608 57.0277 64.1667 55.4169 64.1667H14.5835C12.9727 64.1667 11.6669 62.8608 11.6669 61.25V49.8463L5.88056 18.0217C5.6619 16.8191 6.21637 15.6077 7.26953 14.9871C8.32268 14.3666 9.65106 14.4686 10.5971 15.2426L23.5932 25.8757L32.3032 4.72281C32.7532 3.62993 33.8183 2.91666 35.0002 2.91666ZM17.5002 52.5V58.3333H52.5002V52.5H17.5002ZM52.9827 46.6667L56.9627 24.7764L47.0555 32.8824C46.3404 33.4674 45.3905 33.6791 44.4948 33.453C43.599 33.2269 42.8633 32.5898 42.5115 31.7355L35.0002 13.4937L27.4888 31.7355C27.1371 32.5898 26.4014 33.2269 25.5056 33.453C24.6098 33.6791 23.6599 33.4674 22.9449 32.8824L13.0377 24.7764L17.0177 46.6667H52.9827Z" fill="#F1F1F1"/>
                      </g>
                      </svg>
                  </span> 
                <span  class="greenDollars"  v-else-if="item.element=='greenDollars'">+$</span> 
                <span v-if="item.element != 'crown'" >{{ item.price }}</span>
                </p>
            </div>
      <!-- </template> -->
      </div>
      <div class="dialog__content" v-if="items.length>8">

        
          <template >
            <div class="dialog__first" >
              <template v-for="(item,index) in items" >
                <template v-if="index%2==0">
                    <div class="dialog__item" :key="index">
                      <h5 class="dialog__item-title">{{ item.title }}</h5>
                       <p class="dialog__item-content">
                        <span class="simpleDollars" v-if="item.element=='simpleDollars'">$</span> 
                        <span class="crown" v-else-if="item.element=='crown'">
                          <svg width="44" height="44" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg">
                              <g opacity="0.4">
                              <path fill-rule="evenodd" clip-rule="evenodd" d="M35.0002 2.91666C36.1821 2.91666 37.2472 3.62993 37.6972 4.72281L46.4072 25.8757L59.4032 15.2426C60.3493 14.4686 61.6777 14.3666 62.7308 14.9871C63.784 15.6077 64.3385 16.8191 64.1198 18.0217L58.3335 49.8463V61.25C58.3335 62.8608 57.0277 64.1667 55.4169 64.1667H14.5835C12.9727 64.1667 11.6669 62.8608 11.6669 61.25V49.8463L5.88056 18.0217C5.6619 16.8191 6.21637 15.6077 7.26953 14.9871C8.32268 14.3666 9.65106 14.4686 10.5971 15.2426L23.5932 25.8757L32.3032 4.72281C32.7532 3.62993 33.8183 2.91666 35.0002 2.91666ZM17.5002 52.5V58.3333H52.5002V52.5H17.5002ZM52.9827 46.6667L56.9627 24.7764L47.0555 32.8824C46.3404 33.4674 45.3905 33.6791 44.4948 33.453C43.599 33.2269 42.8633 32.5898 42.5115 31.7355L35.0002 13.4937L27.4888 31.7355C27.1371 32.5898 26.4014 33.2269 25.5056 33.453C24.6098 33.6791 23.6599 33.4674 22.9449 32.8824L13.0377 24.7764L17.0177 46.6667H52.9827Z" fill="#F1F1F1"/>
                              </g>
                              </svg>
                          </span> 
                        <span  class="greenDollars"  v-else-if="item.element=='greenDollars'">+$</span> 
                      <span v-if="item.element != 'crown'" >{{ item.price }}</span>
                      </p>
                          </div>
                </template>
            </template>
            
              
            </div>
          </template>
          <template >
            <div class="dialog__first" >
              <template v-for="(item,index) in items" >
                <template v-if="index%2==0">
                  
                    <div class="dialog__item" :key="index">
                      <h5 class="dialog__item-title">{{ item.title }}</h5>
                       <p class="dialog__item-content">
                      <span class="simpleDollars" v-if="item.element=='simpleDollars'">$</span> 
                      <span class="crown" v-else-if="item.element=='crown'">
                        <svg width="44" height="44" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <g opacity="0.4">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M35.0002 2.91666C36.1821 2.91666 37.2472 3.62993 37.6972 4.72281L46.4072 25.8757L59.4032 15.2426C60.3493 14.4686 61.6777 14.3666 62.7308 14.9871C63.784 15.6077 64.3385 16.8191 64.1198 18.0217L58.3335 49.8463V61.25C58.3335 62.8608 57.0277 64.1667 55.4169 64.1667H14.5835C12.9727 64.1667 11.6669 62.8608 11.6669 61.25V49.8463L5.88056 18.0217C5.6619 16.8191 6.21637 15.6077 7.26953 14.9871C8.32268 14.3666 9.65106 14.4686 10.5971 15.2426L23.5932 25.8757L32.3032 4.72281C32.7532 3.62993 33.8183 2.91666 35.0002 2.91666ZM17.5002 52.5V58.3333H52.5002V52.5H17.5002ZM52.9827 46.6667L56.9627 24.7764L47.0555 32.8824C46.3404 33.4674 45.3905 33.6791 44.4948 33.453C43.599 33.2269 42.8633 32.5898 42.5115 31.7355L35.0002 13.4937L27.4888 31.7355C27.1371 32.5898 26.4014 33.2269 25.5056 33.453C24.6098 33.6791 23.6599 33.4674 22.9449 32.8824L13.0377 24.7764L17.0177 46.6667H52.9827Z" fill="#F1F1F1"/>
                            </g>
                            </svg>
                        </span> 
                      <span  class="greenDollars"  v-else-if="item.element=='greenDollars'">+$</span> 
                <span v-if="item.element != 'crown'" >{{ item.price }}</span>
                </p>
                    </div>
                </template>
            </template>
            
              
            </div>
          </template>
            
          
</div>
  </div>
  </div>
</div>
</template>

<script>



export default {
  name: 'HomeView',
  data(){
    return{
      classContainer:"",
      items:[
        {
          title:"Отправить на стоянку",
          price:"400",
          element:"simpleDollars"

        },
        {
          title:"Отправить на стоянку",
          
          element:"crown"

        },
        {
          title:"Отправить на стоянку",
          price:"98967800",
          element:"greenDollars"
        },
        {
          title:"Отправить на стоянку",
          price:"400",
          element:"simpleDollars"
        },
        {
          title:"Отправить на стоянку",
          price:"400",
          element:"crown"
        },
        {
          title:"Отправить на стоянку",
          price:"44300",
          element:"greenDollars"
        },
        {
          title:"Отправить на стоянку",
          price:"400",
          element:"simpleDollars"
        },
        {
          title:"Отправить на стоянку",
          price:"42300",
          element:"greenDollars"
        }
        // ,
        // {
        //   title:"Отправить на стоянку",
        //   price:"42300",
        //   element:"greenDollars"
        // },
        //   {
        //     title:"Отправить на стоянку",
        //     price:"400",
        //     element:"greenDollars"
        //   },
        //   {
        //     title:"Отправить на стоянку",
        //     price:"400",
        //     element:"greenDollars"
        //   },
        // {
        //   title:"Отправить на стоянку",
        //   price:"400",

        // },
        // {
        //   title:"Отправить на стоянку",
        //   price:"400",

        // },
        // {
        //   title:"Отправить на стоянку",
        //   price:"400",

        // },
        // {
        //   title:"Отправить на стоянку",
        //   price:"400",

        // }

      ]
    }
  },
  components: {
    // HelloWorld
  },
  mounted(){
    if(this.items.length > 8){
      this.classContainer = "dialog__content-bigger"
    }
    else if(this.items.length <= 4){
      this.classContainer = "dialog__content-small"
    }
    console.log(this.classContainer)
  }
}
</script>

<style lang="scss">
.container{
  background-image: url('@/assets/BG.jpg');
  height: 100vh;
  width: 100vw;
}
.dialog{
  margin: 0 auto;
  padding-top: 3em;
  width: 90vw;
  margin-top: 3vh;
  &__first{
    display: flex;
  }
  &__header{
    display: flex;
    align-items: center;

  }
  &__logo{
    color: #F1F1F1;
    font-family: DIN Pro;
    font-size: 3rem;
    font-weight: 700;
    line-height: 80px;
    letter-spacing: 0.02em;
    text-align: left;

  }
  &__title{
    margin-left: 15px;
    color: #f1f1f183;
    font-size:2.2rem;
  }
  &__close{
    margin-left: auto;
    border-radius: 50%;
    width: 30px;
    height: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(180deg, rgba(241, 241, 241, 0.2) -0.13%, rgba(241, 241, 241, 0) 70.14%);
    padding: .4em;
    color:#F1F1F1;
    cursor: pointer;
   
  }
  &__content{
    display: flex;
    margin-top: 2rem;
    flex-wrap: wrap;
    // height: 50vh;
    font-family:DIN Pro;
    font-size: 2rem;
    font-weight: 500;
  
    letter-spacing: 0em;
    color: #F1F1F1;
    text-align: left;
    
    &-bigger{
      width: 100vw;
      overflow-x: scroll;
      flex-wrap: nowrap;
      &::-webkit-scrollbar{
        background-color: transparent;
       
        // height: 100vh;
        // z-index: 100;
      }
      &::-webkit-scrollbar-thumb{
        height: 20px;
        border-radius: 20%;
        background: #505a3a33;
        opacity: .2;
        position: absolute;
        z-index: 20;
      }
    }
    &-small{
      width: 100vw;
     justify-content: center;
     align-items: center;
     display: flex;
     height: 70vh;
    }
  }
  &__item{
    // &:first-child{
    //   margin-left: 0;
    // }
    border-radius: 6px;
    flex-basis: 6em;
    padding: 0.4em;
    margin: 10px;
    min-width: 300px;
    height: 200px;
    display: flex;
    // border: 10px solid #943;
    // background: linear-gradient(to bottom,#141A1E 32%, #141A1E 100%);
    background: linear-gradient(180deg, #141A1E 0%, rgba(20, 26, 30, 0.32) 100%);

    
    flex-direction: column;
    justify-content: space-between;
    &-title{
      font-family: DIN Pro;
      font-size: 1.5rem;
      font-weight: 500;
    
      letter-spacing: 0em;
      text-align: left;

    }
    &-content{
    display: flex;
    align-items: flex-end;
    }
  }
}
.simpleDollars{
 
  color: #FFCD4C;
}
.greenDollars{
  color:#9FD035;
}
</style>
