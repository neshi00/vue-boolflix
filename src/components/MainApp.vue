<template>
  <div class="container">
    <div>
      {{ searchedMovies[0].title }}
      <img src="" />
    </div>
    <movie-poster />
  </div>
</template>

<script>
import MoviePoster from "./MoviePoster.vue";

export default {
  components: {
    MoviePoster,
  },
  props: {
    searchedMovies: Array,
  },
};
</script>

<style lang="scss" scoped>
.container {
  width: 1200px;
  margin: 0 auto;
  height: 600px; //******** */
  background-color: gray;
}
</style>
