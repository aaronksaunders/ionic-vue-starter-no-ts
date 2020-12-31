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
    <ion-button expand="block" @click="save">OK</ion-button
    ><ion-button expand="block" color="danger" @click="cancel"
      >CANCEL</ion-button
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
      content: "Content"
    };
  },
  components: { IonContent, IonHeader, IonTitle, IonToolbar, IonButton }
});
</script>