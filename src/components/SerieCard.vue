<template>
  <div class="card-container">
    <div class="card">
      <div id="show">
        <img
          :src="'https://image.tmdb.org/t/p/original/' + serie.poster_path"
        />
      </div>
      <div id="hide">
        <div class="info">
          <div>{{ serie.original_name }}</div>
          <div id="overview">{{ serie.overview }}</div>

          <div class="info-bottom">{{ serie.original_language }}</div>
          <div class="info-bottom">{{ serie.vote_average }}</div>
        </div>
      </div>
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
        }
      }
    }
  }
}
</style>
