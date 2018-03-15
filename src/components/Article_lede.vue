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
    position: relative;
    .type {
      background-color: $white;
      font-family: $font_mono;
      font-size: 16px;
      left:0;
      padding: 5px 10px 5px 0;
      position: absolute;
      text-transform: uppercase;
      top: 0;
      z-index: 1;
    }
    .headline {
      cursor: pointer;
      font-family: $font_condensed_strong;
      font-size: 76px;
      line-height: .95;
      margin: 0 auto;
      position: relative;
      top: -76px;
      text-transform: uppercase;
      text-align: center;
      width: 90%;
      span {
        background-color: $white;
        padding: 0 10px;
      }
    }
    img {
      position: relative;
      left: 5%;
    }
  }
</style>
