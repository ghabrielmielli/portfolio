<template>
  <router-link :class="isCool ? 'cool' : 'button'" :to="link || '#'">
    <slot></slot>
  </router-link>
</template>
<script>
export default {
  props: {
    link: String,
    isCool: Boolean,
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
  box-shadow: -8px 8px var(--primary);
  border: 2px solid var(--primary);

  transition: 0.3s ease-out;
}
.cool:hover {
  box-shadow: -12px 12px var(--primary);
  transform: translate(4px, -4px);
}
.cool:active {
  box-shadow: 0px 0px var(--primary);
  transform: translate(-12px, 12px);
  transition: 0.05s;
}

a.router-link-active {
  border-bottom: 3px solid var(--primary);
}
</style>