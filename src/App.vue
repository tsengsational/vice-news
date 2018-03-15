<template>
  <div id="app">
    <div class="app-wrapper">
      <Header/>
      <ArticleLede :article="articleLede"/>
      <div class="article-roll">
        <article class="article" v-for="(article, key, index) in articles">
          <ArticleSM :article="article" v-if="(index + 1) % 3 > 0" />
          <ArticleLG :article="article" v-if="(index + 1) % 3 === 0" />
          <Newsletter v-if="index === 1" :newsletter="newsletter" />
        </article>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import ArticleLede from './components/Article_lede'
import ArticleSM from './components/Article_sm'
import ArticleLG from './components/Article_lg'
import Newsletter from './components/Newsletter'

export default {
  name: 'app',
  components: {
    Header,
    ArticleLede,
    ArticleSM,
    ArticleLG,
    Newsletter
  },
  data: function() {
    return {
      articleLede: {
        type: 'extremism',
        headline: 'Austria’s far-right frat boys have made it into government. There’s reason to be freaked out.',
        image: {
          photo: 'https://video-images.vice.com/articles/5aa059c1cc59160008d5ec54/lede/1520961778651-austrian-frats.jpeg?resize=1024:*'
        }
      },
      articles: {
        a: {
          type: 'Vice News Tonight',
          headline: "Why the U.S. is fighting terror organizations in Africa",
          image: {
            photo: "https://video-images.vice.com/articles/5a9d903078e73b00087a7519/lede/1520882828390-VNT_SAHRA.jpeg"
          }
        },
        b: {
          type: "Immigration",
          headline: "ICE spokesman quits rather than make “false” statements for Trump and Sessions",
          image: {
            photo: "https://video-images.vice.com/articles/5aa7e62565cc6a00065be19e/lede/1520954974815-AP_18066613631459.jpeg"
          }
        },
        c: {
          type: "Nerve Agent Attack",
          headline: "What happens when Russia ignores the U.K.’s ultimatum over nerve agent attack",
          image: {
            photo: "https://video-images.vice.com/articles/5aa7f0cb5a48640008d2b2db/lede/1520957532155-AP_18071678189927.jpeg"
          }
        },
        d: {
          type: "Special Election",
          headline: "Trump-backed Pennsylvania Republican Rick Saccone says liberals hate America and God",
          image: {
            photo: "https://video-images.vice.com/articles/5aa7e34f113c9e0008d9eec8/lede/1520952216717-rick-saccone-trump-jr.jpeg"
          }
        },
        e: {
          type: "Vice News Tonight",
          headline: "Putin’s opposition party doesn’t have a candidate. But it has a plan.",
          image: {
            photo: "https://video-images.vice.com/articles/5aa7cab8bb44de000730dadc/lede/1520950938088-PKG_EPS29916_NAVALNY_OPPOSITION_031218_1420_MASTER_LOCKED01_02_27_18Still007.jpeg"
          }
        },
        f: {
          type: "Rex Tillerson",
          headline: "Donald Trump just fired Rex Tillerson on Twitter",
          image: {
            photo: "https://video-images.vice.com/articles/5aa7c87365cc6a00065bdac2/lede/1520945484102-Tillersonfired.jpeg"
          }
        },
        g: {
          type: "United",
          headline: "United accidentally flew a dog to Japan but it’s still alive",
          image: {
            photo: "https://video-images.vice.com/articles/5aa98d5320857600095dbb48/lede/1521061433117-GettyImages-502331184.jpeg"
          }
        }
      },
      newsletter: {
        type: 'Newsletter',
        promo: "Get the best of VICE News delivered to your inbox."
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
