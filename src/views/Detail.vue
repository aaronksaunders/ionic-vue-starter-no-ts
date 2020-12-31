<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start"
          ><ion-back-button default-href="/"></ion-back-button
        ></ion-buttons>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding">
      <ion-button @click="openModal">Open Modal</ion-button>
      <!-- THE MODAL -->
      <ion-modal
        :is-open="modalIsOpen"
        css-class="my-custom-class"
        @onDidDismiss="modalIsOpen = false"
      >
        <simple-modal
          :data="data"
          @modalSave="handleSave"
          @modalCancel="handleCancel"
        ></simple-modal>
      </ion-modal>

      <!-- MODAL RESPONSE TOAST -->
      <ion-toast
        :is-open="toastInfo.isOpen"
        :message="toastInfo.message"
        :duration="2000"
        @onDidDismiss="toastInfo.isOpen = false"
      >
      </ion-toast>
    </ion-content>
  </ion-page>
</template>

<script>
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
  IonBackButton,
  IonButtons,
  IonModal,
  IonToast
} from "@ionic/vue";
import { defineComponent } from "vue";
import SimpleModal from "@/components/SimpleModal.vue";

export default defineComponent({
  name: "Detail",
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonBackButton,
    IonButtons,
    SimpleModal,
    IonModal,
    IonToast
  },
  methods: {
    openModal() {
      this.modalIsOpen = true;
    },
    handleSave() {
      this.modalIsOpen = false;
      this.toastInfo = {
        isOpen: true,
        message: "Modal Was Closeed with OK"
      };
    },
    handleCancel() {
      this.modalIsOpen = false;
      this.toastInfo = {
        isOpen: true,
        message: "Modal Was Cancelled"
      };
    }
  },
  data() {
    return {
      modalIsOpen: false,
      toastInfo: {
        isOpen: false,
        message: ""
      },
      data: {
        name: "Why Data"
      }
    };
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