<template>
  <ion-nav :root="rootPage" id="nav"> </ion-nav>
</template>

<script lang="ts">
import { IonNav } from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "ProfileModal",
  components: {
    IonNav,
  },
  props: {
    rootPage: {
      type: Object,
      required: true,
    },
  },
});
</script>

<style></style>
