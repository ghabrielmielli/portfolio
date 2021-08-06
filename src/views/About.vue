<template>
  <div class="basic-container">
    <titled-icon class="titled-icon" />
    <!-- <div class="divider"></div> -->
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
<style scoped>
.divider {
  width: 1px;
  height: 80%;
  background-color: var(--primary);
  align-self: center;
}

.titled-icon {
  width: 25%;
}
.about-part {
  width: 60%;
  margin-left: 5%;
}
</style>