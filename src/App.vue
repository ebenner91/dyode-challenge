<template>
  <div id="app">
    <Header promoBanner="Free Shipping on all orders"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Lato&family=Pacifico&display=swap');
  
    // Required Core Stylesheet
  @import "node_modules/@glidejs/glide/src/assets/sass/glide.core";

  // Optional Theme Stylesheet
  @import "node_modules/@glidejs/glide/src/assets/sass/glide.theme";


  body {
    margin: 0;
  }

  #app {
    font-family: 'Lato', sans-serif;
  }

  .container {
    padding: 0 20px;
  }

  @media screen and (min-width: 1024px) {
    .container {
      padding: 0 48px;
    }
  }
</style>
