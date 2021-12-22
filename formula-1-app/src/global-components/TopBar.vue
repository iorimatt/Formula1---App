 
 
<template>
  <ion-header :translucent="true">
    <ion-toolbar>
      <ion-grid class="TopBar">
        <ion-row>
          <ion-col> </ion-col>
          <ion-col class="d-flex-end ion-align-self-center">
            <ion-img
              class="logoHome"
              src="https://www.racecar-engineering.com/wp-content/uploads/2018/03/F1-LOGO.png"
            ></ion-img>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-toolbar>
  </ion-header>
</template>

<script>
import {
  IonHeader,
  IonToolbar,
  IonCol,
  IonRow,
  IonGrid,
  IonImg,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "TopBar",
  components: {
    IonImg,
    IonRow,
    IonCol,
    IonGrid,
    IonHeader,
    IonToolbar,
  },
});
</script>

<style>
.TopBar {
  background-color: red;
  color: white;
}

.logoHome {
  height: 80px;
  width: 80px;
  padding: 0px;
}

.d-flex-end {
  display: flex;
  justify-content: end;
}
</style>

 