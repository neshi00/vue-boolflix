<template>
  <div id="app">
    <header-search @search="callApi" />
    <main-app :movieList="movieList" />
  </div>
</template>

<script>
import axios from "axios";
import HeaderSearch from "./components/HeaderSearch.vue";
import MainApp from "./components/MainApp.vue";

export default {
  name: "App",
  components: {
    HeaderSearch,
    MainApp,
  },
  data() {
    return {
      movieList: [],
      api_key: "6f184fdd682e9397025fe5bbc2979a0f",
    };
  },
  methods: {
    callApi(searched) {
      const params = {
        query: searched,
        api_key: this.api_key,
      };

      return axios
        .get(`https://api.themoviedb.org/3/search/movie`, { params })
        .then((response) => {
          console.log(response.data.results);
          this.movieList = response.data.results;
        });
    },
  },
};
</script>

<style lang="scss"></style>
