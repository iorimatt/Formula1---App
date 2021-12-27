<template>


<ion-app>

  <ion-page class="HomePage">
    <top-bar></top-bar>


 

    <!----MainBanner--->

    <ion-content style="margin-bottom: 10px" :fullscreen="true">
      <ion-slides class="HomeBanner" pager="true" :options="slideOpts">
        <ion-slide
          v-for="banner in HomeBanner"
          :key="banner.img"
          :style="{ backgroundImage: 'url(' + banner.img + ')' }"
        >
          <div>
            <ion-row>


              
              <ion-col size="3" style="display: flex"
                ><ion-button  size="lg" class="PlayButton ion-activatable ripple-parent">
                  
                 
                  <ion-icon name="play-circle-outline"></ion-icon
                >
                
                </ion-button>

                  
              </ion-col>
              
              <ion-col size="9" style="display: flex">
                <ion-row >
                 
                  <ion-col>
                   
                   
                    <p class="title">{{ banner.name }}</p>
                    <p class="subtitle">
                      {{ banner.videoDuration }} | {{ banner.linkTo }}
                    </p>
                     
                     
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
        <ion-slide
          class="CarouselCard"
          v-for="banner in BodyCarousel"
          :key="banner.img"
        >
          <div>
            <ion-row>
              <ion-col>
                <div
                  :style="{ backgroundImage: 'url(' + banner.img + ')' }"
                ></div>
                <p class="title">{{ banner.name }}</p>
                <p class="subtitle">
                  {{ banner.videoDuration }} | {{ banner.tag }}
                </p>
              </ion-col>
            </ion-row>
          </div>
        </ion-slide>
      </ion-slides>


<!----Card Row-----> 


      <ion-row class="HeadCarousel">
        <ion-col><h2 class="f1-font">Programas</h2> </ion-col>
        <ion-col><p>Ver Todos</p></ion-col>
        
      </ion-row>


      <ion-row class="ListContents" v-for="banner in ListContent" :key="banner.img">

          <ion-col class="ListImage" size="12" :style="{ backgroundImage: 'url(' + banner.img + ')' }"></ion-col>
          <ion-col size="12"><h2 class="titillium-regular">{{banner.name}}</h2></ion-col>
          <ion-col size="12"><p class="titillium-regular">{{banner.tag}}</p></ion-col>


      </ion-row>

      <ion-row>

        <ion-col size="12"><p class="titillium-regular" style="text-align:center; color:white; font-size: 18px;">Ver Todos</p></ion-col>

      </ion-row>
 
       


    </ion-content>
    
  </ion-page>

</ion-app>
 
</template>

<script >


import {
  IonContent,
  IonPage,
  IonSlide,
  IonSlides,
  IonButton,
  IonApp
} from "@ionic/vue";

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
    IonApp,
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
            
            HomeBanner: [
        {
          name: "INSIDE STORY: Vitória milagrosa de Max em Abu Dhabi",
          tag: "Documentário",
          videoDuration: "00:00:00",
          img: "https://f1tv.formula1.com/image-resizer/image/1000005250-628f93eb-2e87-4d47-be4d-8712e25bdb7e?w=1918&h=816&q=HI&o=L",
        },
        {
          name: "Temporada 2021",
          tag: "Documentário",
          videoDuration: "00:00:00",
          img: "https://f1tv.formula1.com/image-resizer/image/10000004322?w=1918&h=816&q=HI&o=L",
        },
        {
          name: "A ascensão de Lewis Hamilton",
          tag: "Arquivo",
          videoDuration: "00:00:00",
          img: "https://f1tv.formula1.com/image-resizer/image/1000003773-1f13aa00-ddbd-4324-b3ee-25cb40a7d1ef?w=1461&h=626&q=HI&o=L",
        },
         
      ],
            BodyCarousel: [

                {name:'CORRIDA EM 30 - Barein', tag: 'Corrida', videoDuration: '00:23:21', img: 'https://f1tv.formula1.com/image-resizer/image/1000004657-f1633666-ccd6-4efd-b48b-57c469e1b3ba?w=346&h=192&q=HI&o=L'},
                 {name:'CORRIDA EM 30 - Estados Unidos', tag: 'Corrida', videoDuration: '00:23:21', img: 'https://f1tv.formula1.com/image-resizer/image/1000004893-2e2a420b-998e-4a5e-8fac-60a73eb78d7a?w=346&h=192&q=HI&o=L'},
                  {name:'A histórica 100ª vitória de Hamilton', tag: 'Documentário', videoDuration: '00:23:21', img: 'https://f1tv.formula1.com/image-resizer/image/1000004838-242900a9-9155-4fd1-826d-12fdddb0541c?w=346&h=192&q=HI&o=L'},
                   {name:'WEEKEND DEBRIEF - Abu Dhabi', tag: 'Programa', videoDuration: '00:23:21', img: 'https://f1tv.formula1.com/image-resizer/image/1000005244-eccaefb1-6808-4ed4-b6f5-442deda8a84e?w=346&h=192&q=HI&o=L'},


            ],

            ListContent: [

                {name: 'Lendas da Fórmula 1 - Sir Frank Williams', tag: 'Documentário', img: 'https://f1tv.formula1.com/image-resizer/image/1000003160-4b5f8a9d-f35e-4610-a803-5248f3647c3b?w=346&h=192&q=HI&o=L'},
                {name: 'INSIDE STORY: Masterclass de estratégia da Mercedes', tag: 'Documentário', img: 'https://f1tv.formula1.com/image-resizer/image/1000004316-a6056675-adfa-4ff4-9a2a-d384c435e881?w=346&h=192&q=HI&o=L'},
                {name: 'INSIDE STORY: Como Ricciardo conquistou a vitória em Monza', tag: 'Documentário', img: 'https://f1tv.formula1.com/image-resizer/image/1000004788-b1c879f4-8f7a-418e-be97-09e1779f30e2?w=346&h=192&q=HI&o=L'}, 


            ]



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


.ListContents h2 {

color: white;
font-size: 17px;
margin-top: 15px;
margin-bottom: 0px;


}

.ListContents p {

    font-size: 14px;
    margin-top: 5px;
    margin-bottom: 30px;
    color: #8A8A8F;
    border-color: red;
    border: 0px 10px;
    border-style: solid;
    border: 0px 10px 0px 10px;
    border-top: 0px;
    border-left: 0px;
    border-right: 0px;
    padding-bottom: 15px;
    border-width: 1px;


}


.ListImage {
    height: 120px;
    background-size: cover;
    border-radius: 5px;
    width: 100%;

}


.HeadCarousel {
  margin: 20px 10px;
}

.HeadCarousel h2 {
  color: white;
  font-size: 20px;
  text-align: start;
  margin: 0px;
}

.HeadCarousel p {
  color: white;
  font-size: 16px;
  text-align: end;
  margin: 0px;
}

.BodyCarousel .subtitle {
  color: #8a8a8f;
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
  color: #8a8a8f;
  font-size: 14px;
  margin: 0px;
  text-align: start;
}

.HomeBanner .title {
  font-size: 16px;
  text-align: start;
  margin-top: 5px;
  margin-bottom: 0px;
  color: white;
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
  --ion-background-color: #15151e;
}

.HomeBanner div {
  background-color: #15151e;
  width: 80%;
  height: 40%;
  align-self: end;
  margin-bottom: 10%;
  opacity: 0.9;
  border-radius: 5px;
}

.HomeBanner,
.BodyCarousel {
  height: 220px;
  width: 100%;
  background-color: #15151e;
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