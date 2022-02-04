<template>
  <div id="app">
    <header-search @search="callApi" />
    <main-app :searchedMovies="arraySearchedMovies" />
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
      arraySearchedMovies: [],
    };
  },
  methods: {
    callApi() {
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=6f184fdd682e9397025fe5bbc2979a0f&query=future"
        )
        .then((response) => {
          console.log(response.data);
          this.arraySearchedMovies = response.data.results;
        });
    },
    // creare metodo che costruisce path poster
  },
};
</script>

<style lang="scss">
// creare variabile scss per base moviedb
// creare variabile scss per api key
</style>
