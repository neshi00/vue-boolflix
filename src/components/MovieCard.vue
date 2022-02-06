<template>
  <div class="card-container">
    <div class="card">
      <div id="show">
        <img
          :src="'https://image.tmdb.org/t/p/original/' + movie.poster_path"
        />
      </div>
      <div id="hide">
        <div class="info">
          <div>{{ movie.original_title }}</div>
          <div id="overview">{{ movie.overview }}</div>
          <div class="info-bottom">
            <img
              v-if="languages.includes(movie.original_language)"
              :src="`/flags/${movie.original_language}.png`"
            />
            <span v-else {{movie.original_language}}></span>
          </div>
          <div class="info-bottom">VOTO: {{ movie.vote_average }}</div>
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
.card-container {
  background-color: #000;
  width: calc(100% / 5);

  .card {
    padding: 10px;
    color: #fff;

    &:hover {
      #show {
        display: none;
      }

      #hide {
        display: block;
      }
    }

    img {
      width: 100%;
      height: 400px;
    }
    #hide {
      display: none;

      .info {
        font-size: 20px;
        font-weight: bold;
        text-align: center;
        padding: 20px;

        #overview {
          padding: 10px;
          font-size: 10px;
        }

        .info-bottom {
          margin-top: 20px;

          img {
            width: 30px;
            height: 15px;
          }
        }
      }
    }
  }
}
</style>
