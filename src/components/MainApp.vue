<template>
  <div class="container">
    <movie-card v-for="movie in movieList" :key="movie.id" :movie="movie" />

    <serie-card v-for="serie in seriesList" :key="serie.id" :serie="serie" />
  </div>
</template>

<script>
import MovieCard from "./MovieCard.vue";
import SerieCard from "./SerieCard.vue";

export default {
  components: {
    MovieCard,
    SerieCard,
  },
  props: {
    movieList: Array,
    seriesList: Array,
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
