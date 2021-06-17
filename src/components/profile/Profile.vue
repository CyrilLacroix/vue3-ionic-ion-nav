<template>
  <ion-buttons slot="start">
    <ion-button @click="setOpen(true)">
      <ion-icon :icon="personOutline" h="40" w="40" />
    </ion-button>
  </ion-buttons>
  <ion-modal :is-open="isOpenRef" @onDidDismiss="setOpen(false)">
    <ProfileModal :rootPage="ProfileDetail"></ProfileModal>
  </ion-modal>
</template>

<script lang="ts">
import { IonModal, IonButton, IonIcon, IonButtons } from "@ionic/vue";
import { personOutline } from "ionicons/icons";

import { defineComponent, ref } from "vue";
import ProfileModal from "@/components/profile/ProfileModal.vue";
import ProfileDetail from "@/components/profile/ProfileDetail.vue";

export default defineComponent({
  name: "Profile",
  components: { IonModal, IonButton, IonIcon, IonButtons, ProfileModal },
  setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => (isOpenRef.value = state);
    return { isOpenRef, setOpen, personOutline, ProfileDetail };
  },
});
</script>
