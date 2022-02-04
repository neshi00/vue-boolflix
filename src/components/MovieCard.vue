<template>
  <div class="card-container">
    <div class="card">
      <img :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path" />
      <div>{{ movie.title }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: Object,
  },
};
</script>

<style lang="scss" scoped>
.card-container {
  background-color: gray;
  width: calc(100% / 6);

  .card {
    img {
      width: 100%;
    }
  }
}
</style>
