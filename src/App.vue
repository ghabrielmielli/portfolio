<template>
  <div>
    <pretty-canvas>
      <nav-header></nav-header>
      <glass-container>
        <router-view />
      </glass-container>
    </pretty-canvas>
  </div>
</template>

<script>
import GlassContainer from "./components/GlassContainer.vue";
import NavHeader from "./components/NavHeader.vue";
import PrettyCanvas from "./components/PrettyCanvas.vue";
export default {
  name: "App",
  components: {
    NavHeader,
    PrettyCanvas,
    GlassContainer,
  },
};
</script>

<style>
/* @import "./aux/reset.css"; */
@import "./aux/brand.css";
</style>
