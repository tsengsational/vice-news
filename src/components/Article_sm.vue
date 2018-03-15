<template>
  <div class="article-sm">
    <div class="article-sm-image">
      <Photo :photo="article.image.photo"/>
    </div>
    <div class="article-sm-content">
      <div class="type">
        {{article.type}}
      </div>
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

  .article-sm {
    border-top: 1px solid $black;
    position:relative;
    margin: 32px 20px;
    .article-sm-content {
      position: relative;
      left: 110px;
      top: 0;
      width: 60%;
      .type {
        padding: 5px 10px 5px 0;
        font-family: $font_mono;
        font-size: 16px;
        text-transform: uppercase;
      }
      .headline {
        cursor: pointer;
        font-size: 18px;
        font-family: $font_reg;
        margin-top: 7px;
      }
    }
    .article-sm-image > .photo > img {
      position:absolute;
      max-width: 96px;
    }
  }

  @media (min-width: 1000px) {
    .article-sm {
      border-top: 1px solid $black;
      position:relative;
      margin: 64px 0;
      width: auto;
      .article-sm-content {
        position: relative;
        left: 220px;
        top: 0;
        .type {
          padding: 5px 10px 5px 0;
          font-family: $font_mono;
          font-size: 16px;
          text-transform: uppercase;
        }
        .headline {
          cursor: pointer;
          font-size: 30px;
          font-family: $font_reg;
          margin-top: 7px;
        }
      }
      .article-sm-image > .photo > img {
        max-width: 192px;
        position: absolute;
      }
    }
  }
</style>
