<template>
  <nav-bar />
  <router-view class="container mx-auto px-4" />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import NavBar from "@/components/NavBar.vue";

export default defineComponent({
  components: {
    NavBar,
  },
});
</script>

<style lang="scss"></style>
