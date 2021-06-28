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
  min-height: 87vh;
  height: 87vh;
  max-height: 87vh;

  margin: 20px auto;
  padding: 1rem 1rem 1rem 1rem;

  background-color: var(--fundo-principal-glass);
  border: 2px solid var(--fundo-secundario);
  border-radius: 6px;
}
</style>