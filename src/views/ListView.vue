<template>
  <div class="relative z-10">
    <Listpage />
  </div>
  <ImageLayer class="absolute top-0 z-0" />
</template>

<script>
import Listpage from "@/components/Listpage.vue";
import ImageLayer from "@/template/ImageLayer.vue";
export default {
  name: "AboutPage",
  components: {
    Listpage,
    ImageLayer,
  },
};
</script>
