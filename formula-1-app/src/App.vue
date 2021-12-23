<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script>
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  }
});
</script>


<style>



#background-content {

background: #15151E !important;


}

.swiper-container-horizontal>.swiper-pagination-bullets .swiper-pagination-bullet {

background: white;
margin: 0 10px;

}


.swiper-pagination-bullet {


width: 34px !important;
height: 4px !important;
border-radius: 0% !important;


  
}
</style>