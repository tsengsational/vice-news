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
    margin: 32px 0;
  }
  .article-sm-content {
    position: absolute;
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
  }
</style>
