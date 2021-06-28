<template>
  <div class="flex-box">
    <titled-icon class="titled-icon" />
    <div class="divider"></div>
    <about-text class="about-part" />
  </div>
</template>
<script>
import TitledIcon from "@/components/aboutPage/TitledIcon.vue";
import AboutText from "../components/aboutPage/AboutText.vue";
export default {
  components: {
    TitledIcon,
    AboutText,
  },
};
</script>
<style>
.flex-box {
  display: flex;
  width: 100%;
  height: 100%;
}
.divider {
  width: 1px;
  height: 80%;
  background-color: var(--texto-principal);
  align-self: center;
}

.titled-icon {
  width: 25%;
}
.about-part {
  width: 65%;
  padding: 1.5rem;
}
</style>