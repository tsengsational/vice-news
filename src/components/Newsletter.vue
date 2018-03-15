<template>
  <div class="newsletter">
    <div class="newsletter-wrapper">
      <div class="type">
        {{newsletter.type}}
      </div>
      <div class="promo">
        {{newsletter.promo}}
      </div>
      <form class="newsletter-form">
        <input type="text" name="email" value="Email Address">
        <button type="button" name="subscribe">subscribe</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: ['newsletter']
}
</script>

<style lang="scss">
  @import "../assets/styles/settings.scss";

  .newsletter {
    border-top: 1px solid $black;
    left: 5%;
    margin-bottom: 70px;
    padding: 30px 0;
    position: relative;
    width: 90%;
    .promo {
      font-family: $font_strong;
      font-size: 32px;
      line-height: 1;
      margin: 12px 0;
      max-width: 740px;
    }
    .type {
      font-family: $font_mono;
      font-size: 16px;
      padding: 5px 10px 5px 0;
      position: absolute;
      text-transform: uppercase;
      top: 0;
    }
    form {
      width: 100%;
      input {
        border: 3px solid $black;
        box-sizing: border-box;
        color: gray;
        font-family: $font_strong;
        font-size: 18px;
        padding: 15px 15px 13px;
        width: 60%;
      }
      button {
        background-color: $black;
        box-sizing: border-box;
        border: medium none;
        color: $white;
        font-family: $font_condensed_strong;
        font-size: 27px;
        padding: 10px 15px 14px;
        position: relative;
        text-transform: uppercase;
        width: 40%;
        &:hover {
          background-color: rgb(255, 215, 0);
          color: $white;
        }
      }
    }
  }

  @media (min-width: 1000px) {
    .newsletter {
      border-top: 1px solid $black;
      margin-bottom: 70px;
      padding: 30px 0;
      position: relative;
      width: auto;
      left: 0;
      .promo {
        font-family: $font_strong;
        font-size: 40px;
        line-height: 1;
        margin: 12px 0;
        max-width: 740px;
      }
      .type {
        font-family: $font_mono;
        font-size: 16px;
        padding: 5px 10px 5px 0;
        position: absolute;
        text-transform: uppercase;
        top: 0;
      }
      form {
        width: auto;
        input {
          border: 3px solid $black;
          box-sizing: border-box;
          color: gray;
          font-family: $font_strong;
          font-size: 18px;
          padding: 15px 15px 13px;
          width: 75%;
        }
        button {
          background-color: $black;
          box-sizing: border-box;
          border: medium none;
          color: $white;
          font-family: $font_condensed_strong;
          font-size: 27px;
          padding: 10px 15px 14px;
          position: relative;
          text-transform: uppercase;
          width: 25%;
          &:hover {
            background-color: rgb(255, 215, 0);
            color: $white;
          }
        }
      }
    }
  .newsletter {
    border-top: 1px solid $black;
    margin-bottom: 70px;
    padding: 30px 0;
    position: relative;
    .promo {
      font-family: $font_strong;
      font-size: 40px;
      line-height: 1;
      margin: 12px 0;
      max-width: 740px;
    }
    .type {
      font-family: $font_mono;
      font-size: 16px;
      padding: 5px 10px 5px 0;
      position: absolute;
      text-transform: uppercase;
      top: 0;
    }
    form {
      input {
        border: 3px solid $black;
        box-sizing: border-box;
        color: gray;
        font-family: $font_strong;
        font-size: 18px;
        padding: 15px 15px 13px;
        width: 75%;
      }
      button {
        background-color: $black;
        box-sizing: border-box;
        border: medium none;
        color: $white;
        font-family: $font_condensed_strong;
        font-size: 27px;
        padding: 10px 15px 14px;
        position: relative;
        text-transform: uppercase;
        width: 25%;
        &:hover {
          background-color: rgb(255, 215, 0);
          color: $white;
        }
      }
    }
  }
}

</style>
