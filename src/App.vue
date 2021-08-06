<template>
  <div>
    <pretty-canvas>
      <nav-header></nav-header>
      <div class="flex centered">
        <router-view v-slot="{ Component }">
          <transition :name="transitionName" mode="default">
            <component :is="Component" />
          </transition>
        </router-view>
      </div>
    </pretty-canvas>
    <pretty-little-girl-decoration></pretty-little-girl-decoration>
  </div>
</template>

<script>
import router from "./router";
import NavHeader from "./components/NavHeader.vue";
import PrettyCanvas from "./components/PrettyCanvas.vue";
import PrettyLittleGirlDecoration from "./components/PrettyLittleGirlDecoration.vue";
export default {
  name: "App",
  components: {
    NavHeader,
    PrettyCanvas,
    PrettyLittleGirlDecoration,
  },
  data() {
    return {
      transitionName: null,
    };
  },
  watch: {
    $route(to, from) {
      // console.log(router.getRoutes().findIndex((e) => e.path == from.path));
      let routes = router.getRoutes();
      let whereYouAre = routes.findIndex((e) => e.path == from.path);
      let whereYouAreGoingTo = routes.findIndex((e) => e.path == to.path);
      let swipeToTheRight = whereYouAre - whereYouAreGoingTo > 0;

      console.log(swipeToTheRight);
      this.transitionName = swipeToTheRight ? "swiperight" : "swipeleft";
    },
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

.swipeleft-enter-active,
.swipeleft-leave-active {
  transition: transform 1s;
}

.swipeleft-enter-from {
  transform: translateX(100%);
}
.swipeleft-leave-to {
  transform: translateX(-100%);
}

.swipeleft-enter-to,
.swipeleft-leave-from {
  transform: translateX(0);
}

.swiperight-enter-active,
.swiperight-leave-active {
  transition: transform 1s;
}

.swiperight-enter-from {
  transform: translateX(-100%);
}
.swiperight-leave-to {
  transform: translateX(100%);
}

.swiperight-enter-to,
.swiperight-leave-from {
  transform: translateX(0);
}
</style>
