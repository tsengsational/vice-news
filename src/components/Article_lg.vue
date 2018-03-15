<template>
  <div class="article-lg">
    <div class="type">
      {{article.type}}
    </div>
    <div class="article-lg-image">
      <Photo :photo="article.image.photo"/>
    </div>
    <div class="article-lg-content">
      <div class="headline">
        <span>{{article.headline}}</span>
      </div>
    </div>
  </div>
</template>

<script>
  import Photo from './Photo'
  export default {
    props: ['article'],
    components: {
      Photo
    }
  }
</script>

<style lang="scss">
  @import '../assets/styles/settings.scss';

  .article-lg {
    border-top: 1px solid $black;
    position:relative;
    width: 90%;
    left: 5%;
    .type {
      padding: 5px 10px 5px 0;
      font-family: $font_mono;
      font-size: 16px;
      text-transform: uppercase;
      position: absolute;
    }
  }
  .article-lg-content {
    position: relative;
    left: 0%;
    margin: 86px 0;
    top: 0;
    width: 40%;

    .headline {
      background-color: $white;
      cursor: pointer;
      font-size: 7vw;
      font-family: $font_condensed_strong;
      line-height: .91;
      margin-left: -0.14em;
      margin-right: -0.14em;
      padding: 0px 0.14em;
      text-transform: uppercase;
      text-align: left;
      display: inline;
    }
  }
  .article-lg-image {
    padding: 50px 0;
    position: absolute;
    left: 20%;
  }
  .article-lg-image > .photo > img {
    max-width: 70vw;
  }

  @media (min-width: 1000px) {
    .article-lg {
      border-top: 1px solid $black;
      position: relative;
      width: auto;
      left: 0;
      .type {
        padding: 5px 10px 5px 0;
        font-family: $font_mono;
        font-size: 16px;
        text-transform: uppercase;
        position: absolute;
      }
    }
    .article-lg-content {
      position: relative;
      left: 53%;
      margin: 86px 0;
      top: 0;
      width: 47%;

      .headline {
        cursor: pointer;
        font-size: 76px;
        font-family: $font_condensed_strong;
        line-height: .91;
        margin-left: -0.14em;
        margin-right: -0.14em;
        padding: 0px 0.14em;
        text-transform: uppercase;
        text-align: left;
        display: inline;
      }
    }
    .article-lg-image {
      padding: 50px 0;
      position: absolute;
      top: calc(50% - 160px);
      left: 0;
    }
    .article-lg-image > .photo > img {
      max-width: 480px;
    }
  }

</style>
