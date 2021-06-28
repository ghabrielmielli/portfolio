<template>
  <div class="mainDiv">
    <img src="@/assets/pp.jpg" />
    <h1>Ghabriel Mielli</h1>
    <span>(forthcoming)</span>
    <h2>Software Engineer</h2>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
@import "../../aux/brand.css";

img {
  width: 10rem;
  height: 10rem;
  border: 0.3em solid var(--destaque);
  border-radius: 50%;
}
.mainDiv {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
span {
  position: relative;
  top: 1.8rem;
  right: 7rem;
  color: var(--texto-secundario);
  transform: rotate(-15deg);
  font-size: 0.8rem;
}

h1 {
  margin-top: 0.4rem;
  margin-bottom: -0.4rem;
}
</style>