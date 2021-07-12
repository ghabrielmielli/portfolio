<template>
  <div class="basic-container main-content">
    <h1>Hi, I'm Ghabriel, and I like to develop stuff!</h1>
    <h4>
      Currently, I'm studying Software Engineering at UFMS, and I'd love to see
      how's the world out there for web developers! Feel free to contact me for
      internship opportunities.
    </h4>
    <basic-button :style="coolButton">Find me!</basic-button>
  </div>
</template>

<script>
import basicButton from "../components/atoms/basicButton.vue";

export default {
  components: { basicButton },
  data() {
    return {
      coolButton: "cool",
    };
  },
};
</script>
<style scoped>
.main-content {
  display: flex;
  flex-flow: column;
  justify-content: center;
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
</style>
