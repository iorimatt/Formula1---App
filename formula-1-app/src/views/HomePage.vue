<template>
  <ion-page>
    <top-bar></top-bar>
    <ion-slides style="height: 300px; width: 100%; background-color:black;" pager="true" :options="slideOpts">
            <ion-slide>
      <ion-img src="https://cdn.record.pt/images/2021-10/img_476x268$2021_10_06_08_40_01_1912408.jpg"></ion-img>
    </ion-slide>
        
        <ion-slide>
      <h1>Slide 2</h1>
    </ion-slide>
    <ion-slide>
      <h1>Slide 3</h1>
    </ion-slide>
  </ion-slides>
    <ion-content :fullscreen="true"> </ion-content>
  </ion-page>
</template>

<script >
import {IonContent,
IonPage,IonSlide, IonSlides} from "@ionic/vue";

import TopBar from '../global-components/TopBar.vue'


import { defineComponent } from "vue";


export default defineComponent({
  components: {
    IonPage,
    IonContent,
    TopBar,
    IonSlides,
    IonSlide, 
   
   
  },

   setup() {
    // Optional parameters to pass to the swiper instance. See http://idangero.us/swiper/api/ for valid options.
    const slideOpts = {
      initialSlide: 1,
      speed: 200
    };
    return { slideOpts }
  }


});
</script>

<style scoped>



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