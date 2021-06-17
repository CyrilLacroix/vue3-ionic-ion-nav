<template>
  <ion-toolbar color="translucent">
    <ion-buttons slot="start">
      <ion-button @click="goToSettings">
        <ion-icon :icon="settingsOutline" h="40" w="40" />
      </ion-button>
    </ion-buttons>
    <ion-title> Guest</ion-title>
    <ion-buttons slot="primary">
      <ion-button @click="closeModal">
        <ion-icon :icon="closeIcon" h="40" w="40" />
      </ion-button>
    </ion-buttons>
  </ion-toolbar>
  <ion-content fullscreen class="ion-padding">
    <div class="user-logo-container">
      <img src="../../assets/icon.png" height="64" />
    </div>
    <div>
      <ion-text
        >Welcome, you are logged as a guest. You need to register to access all the
        features.</ion-text
      >
    </div>
  </ion-content>
</template>

<script lang="ts">
import {
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton,
  IonText,
  IonButtons,
  IonIcon,
  modalController,
} from "@ionic/vue";
import { close as closeIcon, settingsOutline } from "ionicons/icons";
import { defineComponent, onMounted, ref } from "vue";
import Settings from "@/components/profile/Settings.vue";

export default defineComponent({
  name: "IdeaNew",
  components: {
    IonToolbar,
    IonTitle,
    IonContent,
    IonButton,
    IonText,
    IonButtons,
    IonIcon,
  },
  setup() {
    const modalNav = ref(null);

    onMounted(() => {
      modalNav.value = document.getElementById("nav") as any;
    });

    const goToSettings = () => {
      (modalNav.value as any).push(Settings, {
        modalNav: modalNav,
      });
    };

    const closeModal = async () => {
      await modalController.dismiss();
    };

    return {
      closeIcon,
      settingsOutline,
      closeModal,
      goToSettings,
    };
  },
});
</script>

<style>
.user-logo-container {
  text-align: center;
}

.user-id-container {
  position: absolute;
  bottom: 2px;
}
</style>
