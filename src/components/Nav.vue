<template lang="html">
  <nav>
    <div class="topics">
      <div class="topics-title">
        Topics
      </div>
      <a href="#" v-for="(topic, key) in topics" :key="key">
        {{topic}}
      </a>
    </div>
    <div class="topics">
      <div class="topics-title">
        About
      </div>
      <a href="#">Featured reporters</a>
    </div>
  </nav>
</template>

<script>
export default {
  props: ['topics']
}
</script>

<style lang="scss">
  @import "../assets/styles/settings.scss";

  nav {
    background-color: $white;
    border: 1px solid $black;
    padding: 30px 20px 0 20px;

    a {
      display: block;
      font-family: $font_strong;
      font-size: 36px;
      color: $black;
      line-height: 1;
      text-decoration: none;

      &:hover {
        text-decoration: underline;
      }
    }
    .topics {
      margin-bottom: 35px;
    }

    .topics-title {
      font-family: $font_mono;
      font-size: 14px;
      margin: 0 0 15px;
      text-transform: uppercase;
    }
  }

  @media (min-width: 1000px) {
    nav {
      box-sizing: border-box;
      width: 350px;
    }
  }

</style>
