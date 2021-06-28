<template>
  <div class="mainDiv">
    <img src="@/assets/pp.jpg" />
    <h1>Ghabriel Mielli</h1>
    <s>(soon to be)</s>
    <h2>Software Engineer</h2>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
@import "../../aux/brand.css";

img {
  width: 20%;
  height: 20%;
  border: 0.3em solid var(--destaque);
  border-radius: 50%;
}
.mainDiv {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
s {
  position: relative;
  top: 2rem;
  right: 8rem;
  color: var(--texto-secundario);
  transform: rotate(-15deg);
  font-size: 0.8rem;
}

h1 {
  margin-top: 1rem;
  margin-bottom: 0.1rem;
}
</style>