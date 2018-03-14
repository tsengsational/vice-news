<template>
  <div id="app">
    <div class="app-wrapper">
      <Header/>
      <ArticleLede :article="articleLede"/>
      <div class="tall">
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import ArticleLede from './components/Article_lede'

export default {
  name: 'app',
  components: {
    Header,
    ArticleLede
  },
  data: function() {
    return {
      articleLede: {
        type: 'extremism',
        headline: 'Austria’s far-right frat boys have made it into government. There’s reason to be freaked out.',
        image: {
          photo: 'https://video-images.vice.com/articles/5aa059c1cc59160008d5ec54/lede/1520961778651-austrian-frats.jpeg?resize=1024:*'
        }
      }
    }
  }
}
</script>

<style lang="scss">
@import "assets/styles/settings.scss";
body {
  margin: 0
}

.tall {
  height: 150vh;
}
#app {
  font-family: $font_reg;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $black;
}

@media (min-width: 1000px) {
  .app-wrapper {
    width: 1000px;
    margin: 0 auto;
    position: relative;
  }
}


</style>
