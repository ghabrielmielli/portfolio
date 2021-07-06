<template>
  <div class="canvas">
    <div class="ground" />
    <div class="little-girl">
      <div class="head">
        <div class="eye" />
      </div>
      <div class="body" />
      <div class="left-foot" />
      <div class="right-foot" />
      <div class="arm" />
    </div>
    <glowing-firefly />
  </div>
</template>
<script>
import GlowingFirefly from "./GlowingFirefly.vue";
export default {
  components: { GlowingFirefly },
};
</script>
<style scop
    GlowingFireflyed>
.canvas {
  position: absolute;
  bottom: 0px;
  width: 100%;
  height: 40vh;
  pointer-events: none;
}

.ground {
  position: absolute;
  width: 100%;
  height: 20%;
  background: var(--complement);
  bottom: 0px;
}

.little-girl {
  position: absolute;
  bottom: 20%;
  right: 10%;
  /* border: 2px solid pink; */
  width: 90px;
  height: 250px;
  contain: paint;
}

.body {
  position: absolute;

  bottom: 45px;

  width: 0;
  height: 0;
  border-style: solid;
  border-width: 0 45px 120px 45px;
  border-color: transparent transparent var(--complement) transparent;
}

.left-foot {
  right: 40px;
}
.right-foot {
  right: 40px;
}

.left-foot,
.right-foot {
  position: absolute;

  bottom: -5px;

  width: 0;
  height: 0;
  border-style: solid;
  border-width: 50px 5px 0 5px;
  border-color: var(--complement) transparent transparent transparent;
}

.head {
  contain: paint;
  position: absolute;
  width: 50px;
  height: 50px;
  bottom: 159px;
  right: 16px;

  border-radius: 50%;
  background: var(--complement);

  z-index: 5;
}

.eye {
  position: absolute;
  width: 7px;
  height: 15px;
  top: 10px;
  left: 7px;
  transform: rotate(25deg);

  border-radius: 50%;
  background: var(--primary);

  z-index: 6;
}
.arm {
  position: absolute;
  bottom: 60px;
  right: 30px;
  transform: rotate(-5deg);
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 0 5px 28px 0;
  border-color: transparent var(--dark) transparent transparent;

  z-index: 6;
}
</style>