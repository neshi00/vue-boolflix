<template>
  <div class="card-container">
    <div class="card">
      <img
        src="https://image.tmdb.org/t/p/w342/9aq2sHfkkAFwH0wi4bZasXA8NbS.jpg"
        alt=""
      />

      <div>{{ oneMovie.title }}</div>
      <div>{{ oneMovie.original_title }}</div>
      <div>{{ oneMovie.original_language }}</div>
      <div>{{ oneMovie.vote_count }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    oneMovie: Object,
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
