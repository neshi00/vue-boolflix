<template>
  <div class="container">
    <movie-poster
      v-for="movie in searchedMovies"
      :key="movie"
      :oneMovie="movie"
    />
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
  height: 600px; //******** */
  display: flex;
  flex-wrap: wrap;
}
</style>
