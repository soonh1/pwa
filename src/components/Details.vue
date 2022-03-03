<template>
  <nav class="relative z-10 p-[26px]">
    <p class="text-left text-xl font-bold pl-11">Emne</p>
    <button @click="goBack" class="absolute left-0 top-[35%] ml-[1.2rem]">
      <i class="fa-solid fa-arrow-left fa-xl" aria-hidden="true"></i>
    </button>
  </nav>
  <div class="my-6 mx-6 bg-white h-72">
    <div class="border-b-[1px] border-black m-4 py-2 font-bold text-lg">
      Emne
    </div>
    <p class="mx-4 text-lg">
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book.
    </p>
  </div>
  <div class="my-6 mx-6 bg-white h-72">
    <div class="border-b-[1px] border-black m-4 py-2 font-bold text-lg">
      Relevant emneinformation
    </div>
    <p class="mx-4 text-lg">
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s, when an unknown printer took a galley of type and scrambled it to
      make a type specimen book.
    </p>
  </div>
</template>
<script>
export default {
  methods: {
    goBack() {
      this.$router.go(-1);
    },
  },
};
</script>
<style scoped lang="scss">
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css");
nav {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: white;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
