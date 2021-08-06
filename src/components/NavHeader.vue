<template>
  <header>
    <nav>
      <ul>
        <li v-for="link in links" :key="link.name">
          <basic-button :style="navigationButton" :link="link.path">{{
            link.name
          }}</basic-button>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
import router from "../router";
import basicButton from "./atoms/basicButton.vue";
export default {
  components: { basicButton },
  data() {
    return {
      links: [],
      navigationButton: "navBtn",
    };
  },
  created() {
    this.links = router.getRoutes();
  },
};
</script>
<style scoped>
@import "../aux/brand.css";
header {
  width: 100vw;
  height: 5vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.6rem 0;
}
nav {
  width: 80%;
  display: flex;
  justify-content: center;
}
ul {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  list-style-type: none;
}
</style>