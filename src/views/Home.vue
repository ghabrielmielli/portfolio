<template>
  <div class="main-content">
    <h1>Hi, I'm Ghabriel, and I like to develop stuff!</h1>
    <h4>
      Currently, I'm studying Software Engineering at UFMS, and I'd love to see
      how's the world out there for web developers! Feel free to contact me for
      internship opportunities.
    </h4>
    <router-link class="navBtn" to="/contact">Find me!</router-link>
  </div>
</template>

<script>
export default {};
</script>
<style scoped>
.main-content {
  display: flex;
  flex-flow: column;
  justify-content: center;
  height: 100%;
  padding-left: 2rem;
}
h1 {
  font-family: "Source Sans Pro", sans-serif;
  color: var(--destaque);
}
h4 {
  font-family: "Nunito", sans-serif;
  font-size: 1.4rem;
  font-weight: 100;
  flex-shrink: 10;
  width: 75%;
}
.navBtn {
  color: var(--destaque);
  border-radius: 2px;
  margin: 1rem 0 0 3rem;
  padding: 0.2rem 2rem;
  font-size: 1.8rem;
  text-decoration: none;
  width: fit-content;
  background-color: var(--texto-principal);
  box-shadow: -8px 8px 0 var(--fundo-secundario);
}
</style>
