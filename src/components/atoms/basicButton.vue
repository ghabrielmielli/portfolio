<template>
  <router-link :class="style" :to="link || '#'">
    <slot></slot>
  </router-link>
</template>
<script>
export default {
  props: {
    link: String,
    style: {
      type: String,
      default: "button",
    },
  },
};
</script>
<style scoped>
.button {
  color: var(--primary);
  text-decoration: none;
  transition: 0.2s ease-out;
  cursor: pointer;
}
.button:hover {
  background-color: var(--complement);
  border-radius: 10px;
  padding: 0.2rem 1.6rem;
}

.navBtn {
  color: var(--primary);
  text-decoration: none;
  transition: 0.2s ease-out;
  cursor: pointer;
}
.navBtn:hover:not(.router-link-active) {
  box-shadow: 0 8px 2px -6px var(--light);
  background-color: rgba(1, 1, 1, 0);
}

.cool {
  user-select: none;

  border-radius: 2px;
  margin: 1rem 0 0 3rem;
  padding: 0.2rem 2rem;
  font-size: 1.8rem;
  text-decoration: none;
  width: fit-content;
  cursor: pointer;

  color: var(--primary);
  background-color: var(--dark);
  box-shadow: -3px 3px var(--primary);
  border: 2px solid var(--primary);

  transition: 0.4s ease-out;
}
.cool:hover {
  box-shadow: -5px 5px var(--primary);
  transform: translate(2px, -2px);
}
.cool:active {
  box-shadow: 0px 0px var(--primary);
  transform: translate(-5px, 5px);
  transition: 0.08s;
}

a.router-link-active.navBtn {
  border-bottom: 3px solid var(--primary);
}
</style>