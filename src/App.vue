<template>
  <div id="app">
    <Header promoBanner="Free Shipping on all orders"/>
    <hero-slider/>
    <link-cards>
      <link-card 
      imageAlt="Woman in t-shirt" 
      desktopImageUrl="womens-image.jpg" 
      linkUrl="#" 
      mobileWidth="link-card--mobile-half">
      Women's
      </link-card>
      <link-card 
      imageAlt="Man in t-shirt" 
      desktopImageUrl="mens-image.jpg" 
      linkUrl="#" 
      mobileWidth="link-card--mobile-half">
      Men's
      </link-card>
      <link-card 
      imageAlt="Woman with head cropped out, wearing watch on wrist and holding notebook" 
      desktopImageUrl="accessories-image.jpg" 
      mobileImageUrl="accessories-image-mobile.jpg"
      linkUrl="#" 
      mobileWidth="link-card--mobile-full">
      Accessories
      </link-card>
    </link-cards>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import HeroSlider from './components/Hero.vue'
import LinkCards from './components/LinkCards.vue'
import LinkCard from './components/LinkCard.vue'

export default {
  name: 'App',
  components: {
    Header,
    HeroSlider,
    LinkCards,
    LinkCard
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Lato&family=Pacifico&display=swap');
  
    // Required Core Stylesheet
  @import "node_modules/@glidejs/glide/src/assets/sass/glide.core";

  // Optional Theme Stylesheet
  @import "node_modules/@glidejs/glide/src/assets/sass/glide.theme";

  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
  }

  #app {
    font-family: 'Lato', sans-serif;
  }

  .container {
    padding: 0 20px;
  }

  @media screen and (min-width: 1025px) {
    .container {
      padding: 0 48px;
    }
  }
</style>
