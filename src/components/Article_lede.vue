<template>
  <div class="article-lede">
    <div class="type">
      {{article.type}}
    </div>
    <div class="lede-image">
      <Photo :photo="article.image.photo"/>
    </div>
    <div class="headline">
      <span>{{article.headline}}</span>
    </div>
  </div>
</template>

<script>
import Photo from './Photo'
export default {
  props: ['article'],
  components: {
    Photo
  },
  data: function () {
    return {
    }
  }
}
</script>

<style lang="scss">
  @import "../assets/styles/settings.scss";
    .article-lede {
      width: 90%;
      left: 5%;
      position: relative;
      .type{
        background-color: $white;
        font-family: $font_mono;
        font-size: 16px;
        left:0;
        padding: 5px 10px;
        position: absolute;
        text-transform: uppercase;
        top: 0;
        z-index: 1;
      }
      .headline {
        cursor: pointer;
        font-family: $font_condensed_strong;
        font-size: 7vw;
        line-height: .95;
        margin: 0 auto;
        position: relative;
        top: 0px;
        text-transform: uppercase;
        text-align: left;
        width: 90%;
        span {
          background-color: $white;
        }
      }
      img {
        width: 90%;
        position: relative;
        left: 10%;
        top: 30px;
      }
    }


  @media (min-width: 1000px) {
    .article-lede {
      width: auto;
      left: auto;
      position: relative;
      .type {
        padding: 5px 10px 5px 0;
      }
      .headline {
        font-size: 76px;
        text-align: center;
        top: -76px;
        span {
          padding: 0 10px;
        }
      }
      img {
        position: relative;
        left: 5%;
      }
    }
  }
</style>
