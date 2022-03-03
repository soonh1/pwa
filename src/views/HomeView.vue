<template>
  <router-link to="/about">
    <div>
      <img
        alt="logo"
        src="../assets/Langeland-logo.png"
        class="z-10 w-[50%] lg:w-[25%]"
      />
    </div>
    <ImageLayer class="absolute top-0 z-0" />
  </router-link>
</template>

<script>
import ImageLayer from "@/template/ImageLayer.vue";
export default {
  name: "HomeView",
  components: {
    ImageLayer,
  },
};
</script>
<style scoped>
img {
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
</style>
