<template>
  <ion-toolbar>
    <ion-buttons slot="start">
      <ion-nav-link router-direction="back">
        <ion-icon :icon="chevronBack"></ion-icon>
      </ion-nav-link>
    </ion-buttons>
    <ion-title> Settings</ion-title>
  </ion-toolbar>
  <ion-content fullscreen class="ion-padding">
    <div class="settings-version-container">
      <ion-text>© 2021 - 1.0.0.0 - Production</ion-text>
    </div>
  </ion-content>
</template>

<script lang="ts">
import { IonToolbar, IonTitle, IonContent, IonIcon, IonNavLink } from "@ionic/vue";
import { defineComponent } from "vue";
import { chevronBack } from "ionicons/icons";

export default defineComponent({
  name: "Settings",
  components: { IonToolbar, IonTitle, IonContent, IonIcon, IonNavLink },
  props: {
    modalNav: {
      type: Object,
      required: true,
    },
  },
  setup() {
    return { chevronBack };
  },
  methods: {},
});
</script>

<style scoped>
.settings-version-container {
  position: absolute;
  bottom: 2px;
}
</style>
