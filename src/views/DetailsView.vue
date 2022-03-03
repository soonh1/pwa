<template>
  <div class="relative z-10">
    <Details />
  </div>
  <ImageLayer class="absolute top-0 z-0" />
</template>

<script>
import Details from "@/components/Details.vue";
import ImageLayer from "@/template/ImageLayer.vue";
export default {
  name: "AboutPage",
  components: {
    Details,
    ImageLayer,
  },
};
</script>
