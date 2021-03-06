<template>
  <header>
    <div class="header-wrapper" v-bind:class="{lg: resize}">
      <div class="header-content" v-bind:class="{lg: resize}">
        <div class="grow">
          <img class="logo" src="../assets/logo.svg"/>
        </div>
        <div class="header-promo" v-bind:class="{hide: hide}">
          Watch <strong>VICE News Tonight</strong> on HBO weekdays at 7:30.
        </div>
        <button class="subscribe-btn">Subscribe</button>
        <button class="menu-btn" @click="handleMenuClick" v-bind:class="{menuOpen: menuOpen}">
          <div class="menu-top" @click="handleMenuClick"></div>
          <div class="menu-mid" @click="handleMenuClick"></div>
          <div class="menu-btm" @click="handleMenuClick"></div>
        </button>
      </div>
      <div class="nav" v-bind:class="{open: menuOpen}">
        <Nav :topics="topics" />
      </div>
    </div>
  </header>
</template>

<script>
import Nav from './Nav'

export default {
  components: {
    Nav
  },
  data: function () {
    return {
      resize: true,
      menuOpen: false,
      topics: ['VICE News Tonight', 'Watch', 'Money', 'Donald Trump', 'Technology', 'Immigration', 'Drugs', 'Features', 'Terrorism'],
      windowWidth: 0
    }
  },
  created: function() {
    document.addEventListener('scroll', this.debounce(this.toggleExpand, 10))
    window.addEventListener('onresize', this.setWindowWidth)
    this.setWindowWidth
  },
  computed: {
    hide: function () {
      return !this.resize
    }
  },
  methods: {
    toggleExpand: function() {
      let scroll = document.documentElement.scrollTop
      scroll > 1 ? this.resize = false : this.resize = true;
    },
    debounce: function(func, wait, immediate) {
    	var timeout;
    	return function() {
    		var context = this, args = arguments;
    		var later = function() {
    			timeout = null;
    			if (!immediate) func.apply(context, args);
    		};
    		var callNow = immediate && !timeout;
    		clearTimeout(timeout);
    		timeout = setTimeout(later, wait);
    		if (callNow) func.apply(context, args);
      };
    },
    handleMenuClick: function() {
      this.menuOpen = !this.menuOpen
    },
    setWindowWidth: function () {
      this.windowWidth = window.innerWidth
    }
  }
}
</script>

<style lang="scss">
  @import "../assets/styles/settings.scss";
  header {
    position: sticky;
    top: 0;
    background-color: $white;
    z-index: 2;
  }
  .header-content {
    height: 46px;
    border-bottom: 1px solid $black;
    padding: 5px 0;
    transition: height .3s;
    position: relative;
  }
  .header-promo {
    display: none;
  }
  .header-wrapper {
    position: relative;
  }
  .logo {
    height: 33px;
    margin: 0 5px;
    position: absolute;
    top: calc(50% - (33px / 2));
  }
  .menu-btn {
    border: 0;
    background-color: transparent;
    cursor: pointer;
    height: 35px;
    position: absolute;
    right: 0;
    padding: 0 14px;
    top: calc(50% - 17.5px);
    width: 45px;

    &.menuOpen {
      .menu-top {
        transform: rotate(45deg);
        transform-origin: left center 0px;
      }
      .menu-mid {
        opacity: 0;
      }
      .menu-btm {
        transform: rotate(-45deg);
        transform-origin: left center 0px;
      }
    }
  }
  .menu-btn>.menu-top, .menu-mid, .menu-btm {
    background-color: $black;
    height: 4px;
    margin-bottom: 2px;
    transition: transform .3s, opacity .3s;
    width: 17px;
  }

  .nav {
    overflow: hidden;
    opacity: 0;
    right: 0;
    position: absolute;
    transform: translateY(-110%);
    transition: all 0.6s cubic-bezier(0.19, 1, 0.22, 1) 0s;
    width: 100%;
  }

  .nav.open {
    overflow: auto;
    opacity: 1;
    right: 0;
    top: calc(56px - 2px);
    transform: translateY(0px);
  }

  .subscribe-btn {
    display: none;
  }

  @media (min-width: 1000px) {
    .header-promo {
      display: block;
      font-size: 18px;
      position: absolute;
      text-align: center;
      top: calc(50% - 10px);
      transition: opacity .3s;
      width: 100%;
      strong {
        font-family: $font_strong;
      }
      &.hide {
        opacity: 0;
      }
    }
    .header-content {
      margin: 0 auto;
      width: 960px;
      padding: 8px 20px;
      position: relative;
    }
    .header-wrapper {
      margin: 0 auto;
      width: 1000px;
      &.lg .nav.open {
        top: calc(116px - 2px)
      }
    }
    .header-content.lg {
      height: 98px;
    }
    .grow {
      left: 0px;
      display: block;
      position: absolute;
      top: calc(50% - 16.5px)
    }

    .logo {
      position: static;
      margin: 0;
    }
    .nav {
      width: 350px;
      transform: translateY(-120%);
      &.open {
        top: calc(64px - 2px);
      }
    }

    .subscribe-btn {
      display:block;
      background-color: transparent;
      border: 1px solid $black;
      border-radius: 3px;
      font-size: 16px;
      color: $black;
      padding: 4px 15px 5px;
      position: absolute;
      right: 45px;
      top: calc(50% - 15.5px);
      transition: background-color .2s, color .2s;
    }

    .subscribe-btn:hover {
      background-color: $black;
      color: $white;
    }
  }


</style>
