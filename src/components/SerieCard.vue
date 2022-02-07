<template>
  <div class="card-container">
    <div class="card">
      <div id="show">
        <img
          v-if="serie.poster_path === null"
          src="/images/not-available.jpeg"
        />

        <img
          v-else
          :src="'https://image.tmdb.org/t/p/original/' + serie.poster_path"
        />
      </div>
      <div id="hide">
        <div class="info">
          <div>{{ serie.original_name }}</div>
          <div id="overview">{{ serie.overview }}</div>

          <div class="details">
            <span>LINGUA: </span>
            <img
              v-if="languages.includes(serie.original_language)"
              :src="`/flags/${serie.original_language}.png`"
            />
            <p v-else>{{ serie.original_language }}></p>
          </div>

          <div class="details">
            <span>VOTO:</span>
            <i
              v-for="index in Math.round(serie.vote_average / 2)"
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
    serie: Object,
    languages: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "../style/cssCard.scss";
</style>
