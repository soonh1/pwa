<template>
  <div class="relative z-10">
    <kategori1Comp />
  </div>
  <ImageLayer class="absolute top-0 z-0" />
</template>

<script>
import kategori1Comp from "@/components/kategori1Comp.vue";
import ImageLayer from "@/template/ImageLayer.vue";
export default {
  name: "AboutPage",
  components: {
    kategori1Comp,
    ImageLayer,
  },
};
</script>
