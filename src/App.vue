<template>
  <div id="app">
    <header-search @search="generalSearch" />
    <main-app :movieList="movieList" :seriesList="seriesList" />
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
      seriesList: [],
      api_key: "6f184fdd682e9397025fe5bbc2979a0f",
    };
  },
  methods: {
    searchMovie(searched) {
      const params = {
        query: searched,
        api_key: this.api_key,
      };

      return axios
        .get(`https://api.themoviedb.org/3/search/movie`, { params })
        .then((response) => {
          this.movieList = response.data.results;
          console.log(response.data.results);
        });
    },

    searchSerie(searched) {
      const params = {
        query: searched,
        api_key: this.api_key,
      };

      return axios
        .get(`https://api.themoviedb.org/3/search/tv`, { params })
        .then((response) => {
          this.seriesList = response.data.results;
        });
    },

    generalSearch(searched) {
      this.searchMovie(searched);
      this.searchSerie(searched);
    },
  },
};
</script>

<style lang="scss"></style>
