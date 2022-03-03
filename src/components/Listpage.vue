<template>
  <nav class="relative z-10">
    <img
      alt="logo"
      src="../assets/Langeland-logo-white.jpg"
      class="w-[40%] lg:w-[10%] m-auto"
    />
    <router-link to="/about" class="absolute left-0 top-[35%] ml-[1.2rem]">
      <button class="backbutton">
        <i class="fa-solid fa-arrow-left fa-xl" aria-hidden="true"></i>
      </button>
    </router-link>
  </nav>
  <!-- search field -->
  <div class="filter">
    <input type="text" v-model="username" placeholder="Søg her.." />
  </div>
  <!-- filter countries by name and category -->
  <ul class="wrapper my-6 mx-10 text-white h-[350px]">
    <div class="border-b-2 border-white pb-2 font-bold">
      Senest anvendte kort
    </div>
    <li v-for="item in test" :key="item.username" class="my-2">
      <router-link
        :to="`/Details/${item.username}`"
        class="flex justify-between items-center"
      >
        <div class="text">
          <p style="font-weight: bold">{{ item.first_name }}</p>
          <p>Køn : {{ item.gender }}</p>
          <p>Fødselsdag : {{ item.date_of_birth }}</p>
        </div>
        <div>
          <img class="w-14 bg-white" :src="item.avatar" alt="" />
        </div>
      </router-link>
    </li>
  </ul>
  <!-- 4 box -->
  <div class="grid grid-cols-2 gap-3 text-center">
    <router-link to="/kategori1">
      <div class="bg-white p-3">
        <i class="fa-solid fa-handshake-angle fa-4x text-blue-800"></i>
        <p class="font-bold">Kategori 1</p>
      </div>
    </router-link>
    <router-link to="/">
      <div class="bg-white p-3">
        <i class="fa-solid fa-clipboard-list fa-4x text-blue-800"></i>
        <p class="font-bold">Kategori 2</p>
      </div>
    </router-link>
    <router-link to="/">
      <div class="bg-white p-3">
        <i class="fa-solid fa-truck-medical fa-4x text-blue-800"></i>
        <p class="font-bold">Kategori 3</p>
      </div>
    </router-link>
    <router-link to="/">
      <div class="bg-white p-3">
        <i class="fa-solid fa-bandage fa-4x text-blue-800"></i>
        <p class="font-bold">Kategori 4</p>
      </div>
    </router-link>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      RandomUser: [],
      name: "",
      username: "",
    };
  },
  computed: {
    test: function () {
      return this.RandomUser.filter(
        (item) => !item.username.indexOf(this.username)
      );
    },
  },
  created() {
    axios
      .get("https://random-data-api.com/api/users/random_user?size=4")
      .then((response) => {
        this.RandomUser = response.data;
      })
      .catch((err) => console.log(err));
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

//nyt css

.filter {
  display: flex;
  justify-content: space-between;
  margin: 25px 25px 0 25px;
  input {
    padding: 15px;
    width: 25rem;
    border-radius: 5px;
    border-style: none;
    &:focus {
      outline: none;
    }
  }
  select {
    padding: 15px;
    width: 10rem;
    border-radius: 5px;
    border-style: none;
    &:focus {
      outline: none;
    }
  }
}
</style>
