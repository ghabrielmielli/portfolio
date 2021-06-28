<template>
  <div>
    <pretty-canvas>
      <nav-header></nav-header>
      <div class="flex centered">
        <glass-container class="centered">
          <router-view />
        </glass-container>
      </div>
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

.flex {
  display: flex;
}
.centered {
  height: 100%;
  width: 100%;
  align-self: center;
  /* border: 4px solid pink; */
}
</style>
