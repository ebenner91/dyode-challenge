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
    <product-slider>
      <glide-slide>
        <img src="./assets/product-image.jpg">
        <p class="product-slider__title">Product Title</p>
        <p class="product-slider__category">Women's T-Shirt</p>
        <p class="product-slider__price">$19.99</p>
      </glide-slide>
      <glide-slide>
        <img src="./assets/product-image.jpg">
        <p class="product-slider__title">Product Title</p>
        <p class="product-slider__category">Women's T-Shirt</p>
        <p class="product-slider__price">$19.99</p>
      </glide-slide>
      <glide-slide>
        <img src="./assets/product-image.jpg">
        <p class="product-slider__title">Product Title</p>
        <p class="product-slider__category">Women's T-Shirt</p>
        <p class="product-slider__price">$19.99</p>
      </glide-slide>
      <glide-slide>
        <img src="./assets/product-image.jpg">
        <p class="product-slider__title">Product Title</p>
        <p class="product-slider__category">Women's T-Shirt</p>
        <p class="product-slider__price">$19.99</p>
      </glide-slide>
    </product-slider>
    <static-hero/>
    <square-image-slider title="Follow us on Instagram">
      <glide-slide><img src="./assets/social-1.jpg" alt="Instagram Photo"></glide-slide>
      <glide-slide><img src="./assets/social-2.jpg" alt="Instagram Photo"></glide-slide>
      <glide-slide><img src="./assets/social-3.jpg" alt="Instagram Photo"></glide-slide>
      <glide-slide><img src="./assets/social-4.jpg" alt="Instagram Photo"></glide-slide>
      <glide-slide><img src="./assets/social-5.jpg" alt="Instagram Photo"></glide-slide>
    </square-image-slider>
    <newsletter-footer headerText="Sign up &amp; Stay Connected"><p>Sign up for the newsletter and get 20% off! Gain access to exclusive offers and be the first to know when new stuff drops!</p></newsletter-footer>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import HeroSlider from './components/Hero.vue'
import LinkCards from './components/LinkCards.vue'
import LinkCard from './components/LinkCard.vue'
import ProductSlider from './components/ProductSlider.vue'
import GlideSlide from './components/GlideSlide.vue'
import StaticHero from './components/StaticHero.vue'
import SquareImageSlider from './components/SquareImageSlider.vue'
import NewsletterFooter from './components/NewsletterFooter.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    HeroSlider,
    LinkCards,
    LinkCard,
    ProductSlider,
    GlideSlide,
    StaticHero,
    SquareImageSlider,
    NewsletterFooter,
    Footer
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Lato&family=Pacifico&display=swap');
  
    // Required Core Stylesheet
  @import "node_modules/@glidejs/glide/src/assets/sass/glide.core";



  * {
    box-sizing: border-box;
  }

  img {
    max-width: 100%;
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
