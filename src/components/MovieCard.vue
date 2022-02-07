<template>
  <div class="card-container">
    <div class="card">
      <div id="show">
        <img
          v-if="movie.poster_path === null"
          src="/images/not-available.jpeg"
        />

        <img
          v-else
          :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"
        />
      </div>
      <div id="hide">
        <div class="info">
          <div>{{ movie.original_title }}</div>
          <div id="overview">{{ movie.overview }}</div>

          <div class="details">
            <span>LINGUA:</span>
            <img
              v-if="languages.includes(movie.original_language)"
              :src="`/flags/${movie.original_language}.png`"
            />
            <span v-else {{movie.original_language}}></span>
          </div>

          <div class="details">
            <span>VOTO:</span>
            <i
              v-for="index in Math.round(movie.vote_average / 2)"
              :key="index"
              class="fas fa-star"
            ></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object,
    languages: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/cssCard.scss";
</style>
