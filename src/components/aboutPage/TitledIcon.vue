<template>
  <div class="mainDiv">
    <img src="@/assets/pp.jpg" />
    <h1>Ghabriel Mielli</h1>
    <span>forthcoming</span>
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
  border: 1px solid var(--primary);
  border-radius: 50%;
}
.mainDiv {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
span {
  font-family: "Josefin Sans", sans-serif;
  position: relative;
  top: 1.7rem;
  right: 5.5rem;
  color: var(--light);
  transform: rotate(-15deg);
  font-size: 0.8rem;
}

h1 {
  margin-top: 0.4rem;
  margin-bottom: -0.4rem;
}
</style>