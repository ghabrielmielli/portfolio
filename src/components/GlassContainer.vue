<template >
  <div class="basic-container">
    <slot></slot>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
@import "../aux/brand.css";
.basic-container {
  width: 90vw;
  height: 70vh;

  margin: 20px auto;
  padding: 1rem 1rem 1rem 1rem;

  background-color: var(--fundo-principal-glass);
  border-radius: 4px;
}
</style>