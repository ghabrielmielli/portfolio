<template>
  <div>
    <pretty-canvas>
      <nav-header></nav-header>
      <glass-container>
        <main-content></main-content>
      </glass-container>
    </pretty-canvas>
  </div>
</template>

<script>
import GlassContainer from "./components/GlassContainer.vue";
import MainContent from "./components/MainContent.vue";
import NavHeader from "./components/NavHeader.vue";
import PrettyCanvas from "./components/PrettyCanvas.vue";
export default {
  name: "App",
  components: {
    NavHeader,
    PrettyCanvas,
    GlassContainer,
    MainContent,
  },
};
</script>

<style>
/* @import "./aux/reset.css"; */
@import "./aux/brand.css";
</style>
