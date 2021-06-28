<template>
  <header>
    <nav>
      <ul>
        <li v-for="link in links" :key="link.name">
          <router-link class="navBtn" :to="link.path">{{
            link.name
          }}</router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>
<script>
import router from "../router";
export default {
  data() {
    return {
      links: [],
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
  max-width: 100vw;
  min-height: 3vh;
  max-height: 3vh;
  background-color: var(--fundo-principal);
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
  margin: 0;
  padding: 0;
}
li {
  margin: 0 1rem;
}
.navBtn {
  color: var(--destaque);
  border: 2px solid var(--texto-principal);
  border-radius: 6px;
  padding: 0.2rem 2rem;
  text-decoration: none;
}
</style>