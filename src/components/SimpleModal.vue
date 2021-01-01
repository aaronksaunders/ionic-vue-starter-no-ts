<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>{{ title }}</ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content class="ion-padding">
    <div style="padding : 16px">
      {{ content }}
    </div>
    <!-- ok -->
    <ion-button expand="block" @click="save">
      <ion-icon :icon="checkmarkDoneCircleOutline" slot="start"></ion-icon
      >OK</ion-button
    >
    <!-- cancel -->
    <ion-button expand="block" color="danger" @click="cancel">
      <ion-icon :icon="closeCircleOutline" slot="start"></ion-icon>
      CANCEL</ion-button
    >
  </ion-content>
</template>

<script>
import {
  IonContent,
  IonHeader,
  IonTitle,
  IonToolbar,
  IonButton
} from "@ionic/vue";
import { checkmarkDoneCircleOutline, closeCircleOutline } from "ionicons/icons";
import { defineComponent } from "vue";

export default defineComponent({
  name: "SimpleModal",
  props: {
    title: { type: String, default: "Super Modal" }
  },
  methods: {
    save() {
      this.$emit("modal-save");
    },
    cancel() {
      this.$emit("modal-cancel");
    }
  },
  data() {
    return {
      checkmarkDoneCircleOutline,
      closeCircleOutline,
      content: "Content"
    };
  },
  components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton }
});
</script>