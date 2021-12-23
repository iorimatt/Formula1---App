<template>
  <ion-page class="HomePage">
    <top-bar></top-bar>

<!----MainBanner---> 

 <ion-content style="margin-bottom: 10px;" :fullscreen="true"> 
    <ion-slides class="HomeBanner" pager="true" :options="slideOpts">
      <ion-slide v-for="banner in BannersImg" :key="banner.img" :style= "{ backgroundImage:'url(' + banner.img + ')' }">

          <div>

              <ion-row>

                <ion-col size="3" style="display:flex"><ion-button size="lg" class="PlayButton"> <ion-icon name="play-circle-outline"></ion-icon></ion-button> </ion-col>
                <ion-col size="9" style="display:flex"> 

                       <ion-row>
                         <ion-col>
                      <p class="title">{{banner.name}}</p>
                      <p class="subtitle">{{banner.videoDuration}} | {{banner.tag}}</p>
                          </ion-col>
                       </ion-row>

                     
                   </ion-col>

              </ion-row>
              

          </div>

      </ion-slide>

      
    </ion-slides>

  
    
    <!----Body Carousel---> 


<ion-row class="HeadCarousel">

  <ion-col><h2 class="f1-font">Em Destaque</h2> </ion-col>
 <ion-col><p>Ver Todos</p></ion-col>

</ion-row>

   <ion-slides class="BodyCarousel" pager="true" :options="slideBody">
      <ion-slide class="CarouselCard" v-for="banner in BannersImg" :key="banner.img" >

          <div>

              <ion-row>

               <ion-col>

                  <div :style= "{ backgroundImage:'url(' + banner.img + ')' }"></div>
                  <p class="title">{{banner.name}}</p>
                  <p class="subtitle">{{banner.videoDuration}} | {{banner.tag}}</p>



               </ion-col>

              </ion-row>
              

          </div>

      </ion-slide>

      
    </ion-slides>

    </ion-content>

    

    
    
  </ion-page>
</template>

<script >
import { IonContent, IonPage, IonSlide, IonSlides,IonButton, } from "@ionic/vue";

import TopBar from "../global-components/TopBar.vue";


import { defineComponent } from "vue";


export default defineComponent({
  components: {
    IonPage,
    IonContent,
    TopBar,
    IonSlides,
    IonSlide,
    IonButton,
   
    
  },

  setup() {
    // Optional parameters to pass to the swiper instance. See http://idangero.us/swiper/api/ for valid options.
    const slideOpts = {
      initialSlide: 0,
      speed: 200,
      slidesPerView: 1,
    };
    

    const slideBody = {
      speed: 200,
      slidesPerView: 3,
      pagination: false, 
      loop: true, 
      loopAdditionalSlides: 1,
      
      
      
      
    };

return { slideOpts, slideBody };

  },


  data() {
    return {
      BannersImg: [
        { name:"INSIDE STORY: Vitória milagrosa de Max em Abu Dhabi", tag:"Documentário",videoDuration: "00:00:00", img: "https://f1tv.formula1.com/image-resizer/image/1000005250-628f93eb-2e87-4d47-be4d-8712e25bdb7e?w=1918&h=816&q=HI&o=L" }, 
      { name:"Temporada 2021", tag:"Documentário", videoDuration: "00:00:00", img: "https://f1tv.formula1.com/image-resizer/image/10000004322?w=1918&h=816&q=HI&o=L" }, 
      { name:"A ascensão de Lewis Hamilton", tag:"Arquivo", videoDuration: "00:00:00", img: "https://f1tv.formula1.com/image-resizer/image/1000003773-1f13aa00-ddbd-4324-b3ee-25cb40a7d1ef?w=1461&h=626&q=HI&o=L" },
      { name:"A ascensão de Lewis Hamilton", tag:"Arquivo", videoDuration: "00:00:00", img: "https://f1tv.formula1.com/image-resizer/image/1000003773-1f13aa00-ddbd-4324-b3ee-25cb40a7d1ef?w=1461&h=626&q=HI&o=L" },
      { name:"A ascensão de Lewis Hamilton", tag:"Arquivo", videoDuration: "00:00:00", img: "https://f1tv.formula1.com/image-resizer/image/1000003773-1f13aa00-ddbd-4324-b3ee-25cb40a7d1ef?w=1461&h=626&q=HI&o=L" },
      
      ],
    };
  },
});


</script>



<style scoped>


ion-icon {

  font-size: 35px;


}

ion-slide {
  height: 85%;
  background-size: cover;
  background-repeat: no-repeat;
  
}



.HeadCarousel {

margin: 20px 10px;

}

.HeadCarousel h2{

  color: white; 
  font-size: 20px;
  text-align: start;
  margin: 0px;


}

.HeadCarousel p{

  color: white; 
  font-size: 16px;
  text-align: end;
  margin: 0px;


}


.BodyCarousel .subtitle {

color:#8A8A8F; 
font-size: 14px; 
margin: 0px;
text-align: start;


}


.BodyCarousel .title {


color: white; 
font-size: 16px;
text-overflow: ellipsis;
   overflow: hidden;
   white-space: nowrap;
   width: 160px;
   text-align: start;

}


.BodyCarousel {

margin: 10px 0px; 


}


.CarouselCard div {

  height: 126px; 
  width: 146px;
  background-size: cover; 
  background-repeat: no-repeat; 
  border-radius: 5px;


}


.CarouselCard {

margin: 0px 24px;
height: 15vh;


}


.HomeBanner .subtitle {

color:#8A8A8F; 
font-size: 14px; 
margin: 0px;
text-align: start;


}


.HomeBanner .title {

font-size: 16px;
text-align: start;
margin-top: 5px;
margin-bottom: 0px;
color:white;
 text-overflow: ellipsis;
   overflow: hidden;
   white-space: nowrap;
   width: 180px;


}



.PlayButton {

--background: red;
--border-radius: 0px 20px 0px 0px;
height: 55px;


}

.HomePage {


    --ion-background-color:#15151E;


}


.HomeBanner div {


background-color: #15151E;
    width: 80%;
    height: 30%;
    align-self: end;
    margin-bottom: 10%;
    opacity: 0.9;
    border-radius: 5px;

}


.HomeBanner, .BodyCarousel {
  height: 280px;
  width: 100%;
  background-color: #15151E;
  margin-right: 100px;
}

#container {
  text-align: center;

  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;

  color: #8c8c8c;

  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>