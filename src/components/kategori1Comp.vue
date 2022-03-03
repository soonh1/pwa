<template>
  <nav class="relative z-10 p-[26px]">
    <p class="text-left text-xl font-bold pl-11">Kategori 1</p>
    <router-link to="/list" class="absolute left-0 top-[35%] ml-[1.2rem]">
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
    <li v-for="item in test" :key="item.username" class="my-2">
      <router-link
        :to="`/Details/${item.username}`"
        class="flex justify-between items-center"
      >
        <div class="text">
          <p style="font-weight: bold">{{ item.first_name }}</p>
          <p>Job : {{ item.employment.title }}</p>
          <p>Address : {{ item.address.city }}</p>
        </div>
        <div>
          <img class="w-14 bg-white" :src="item.avatar" alt="" />
        </div>
      </router-link>
    </li>
  </ul>
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
      .get("https://random-data-api.com/api/users/random_user?size=7")
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
