<template>
  <div class="relative z-10">
    <Aboutpage />
  </div>
  <ImageLayer class="absolute top-0 z-0" />
</template>

<script>
import Aboutpage from "@/components/Aboutpage.vue";
import ImageLayer from "@/template/ImageLayer.vue";
export default {
  name: "AboutPage",
  components: {
    Aboutpage,
    ImageLayer,
  },
};
</script>
