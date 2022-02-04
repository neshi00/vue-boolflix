<template>
  <div class="container">
    <movie-card v-for="movie in movieList" :key="movie.id" :movie="movie" />
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";

export default {
  components: {
    MovieCard,
  },
  props: {
    movieList: Array,
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
