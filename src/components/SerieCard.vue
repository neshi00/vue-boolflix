<template>
  <div class="card-container">
    <div class="card">
      <img :src="'https://image.tmdb.org/t/p/original/' + serie.poster_path" />
      <div>{{ serie.original_name }}</div>
      <div>{{ serie.original_language }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    serie: Object,
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
