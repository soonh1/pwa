<template>
  <nav class="relative z-10">
    <img
      alt="logo"
      src="../assets/Langeland-logo-white.jpg"
      class="w-[40%] lg:w-[10%] m-auto"
    />
  </nav>
  <div class="px-10 py-12 text-white">
    <div class="border-b-2 border-white pb-2">Vælg din faggruppe</div>
    <router-link to="/list">
      <div
        class="border-b-2 border-white py-2 flex items-center justify-between"
      >
        <p>SOSU</p>
        <i class="fa-solid fa-angle-right"></i>
      </div>
    </router-link>
    <router-link to="/">
      <div
        class="border-b-2 border-white py-2 flex items-center justify-between"
      >
        <p>Sygeplejerske</p>
        <i class="fa-solid fa-angle-right"></i>
      </div>
    </router-link>
    <router-link to="/">
      <div
        class="border-b-2 border-white py-2 flex items-center justify-between"
      >
        <p>Faggruppe 1</p>
        <i class="fa-solid fa-angle-right"></i>
      </div>
    </router-link>
    <router-link to="/">
      <div
        class="border-b-2 border-white py-2 flex items-center justify-between"
      >
        <p>Faggruppe 2</p>
        <i class="fa-solid fa-angle-right"></i>
      </div>
    </router-link>
    <router-link to="/">
      <div
        class="border-b-2 border-white py-2 flex items-center justify-between"
      >
        <p>Faggruppe 3</p>
        <i class="fa-solid fa-angle-right"></i>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css");
nav {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 16px;
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
