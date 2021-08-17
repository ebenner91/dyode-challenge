<template>
  <glide-slider>
    <glide-slide>
      <div class="hero-slider__relative-container">
        <div id="hero-slide-1" class="hero-slider__slide-content"></div>
        <div class="hero-slider__text-overlay">
          <h2 class="hero-slider__heading-text">Shop New Arrivals</h2>
          <p class="hero-slider__info-text">
            Our coolest new items are waiting for you!
          </p>
          <a href="#" class="hero-slider__cta-button">Shop Now</a>
        </div>
      </div>
    </glide-slide>
    <glide-slide>
      <div class="hero-slider__relative-container">
        <div id="hero-slide-1" class="hero-slider__slide-content"></div>
        <div class="hero-slider__text-overlay">
          <h2 class="hero-slider__heading-text">Shop New Arrivals</h2>
          <p class="hero-slider__info-text">
            Our coolest new items are waiting for you!
          </p>
          <a href="#" class="hero-slider__cta-button">Shop Now</a>
        </div>
      </div>
    </glide-slide>
    <glide-slide>
      <div class="hero-slider__relative-container">
        <div id="hero-slide-1" class="hero-slider__slide-content"></div>
        <div class="hero-slider__text-overlay">
          <h2 class="hero-slider__heading-text">Shop New Arrivals</h2>
          <p class="hero-slider__info-text">
            Our coolest new items are waiting for you!
          </p>
          <a href="#" class="hero-slider__cta-button">Shop Now</a>
        </div>
      </div>
    </glide-slide>
  </glide-slider>
</template>

<script>
import GlideSlider from "./GlideSlider";
import GlideSlide from "./GlideSlide";

export default {
  components: {
    GlideSlider,
    GlideSlide,
  },
};
</script>

<style lang="scss" scoped>

.hero-slider__relative-container {
    position: relative;
}

.hero-slider__slide-content {
  padding: 1px;
  height: 60vw;
}

#hero-slide-1 {
  background-image: url("../assets/hero-image-1.jpg");
  background-position: right;
  background-size: cover;
  background-repeat: no-repeat;
}

@media screen and (min-width: 1025px) {
  .hero-slider__slide-content {
    height: 80vh;
  }

  .hero-slider__text-overlay {
    position: absolute;
    top: 50%;
    left: 130px;
    transform: translateY(-50%);
  }
}
</style>