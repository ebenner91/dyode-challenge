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
        <div id="hero-slide-2" class="hero-slider__slide-content"></div>
        <div
          class="
            hero-slider__text-overlay hero-slider__text-overlay--desktop-white
          "
        >
          <h2 class="hero-slider__heading-text">Our Fave Tees</h2>
          <p class="hero-slider__info-text">Shop all of our favorites.</p>
          <a href="#" class="hero-slider__cta-button">Shop Now</a>
        </div>
      </div>
    </glide-slide>
    <glide-slide>
      <div class="hero-slider__relative-container">
        <div id="hero-slide-3" class="hero-slider__slide-content"></div>
        <div
          class="
            hero-slider__text-overlay hero-slider__text-overlay--desktop-white
          "
        >
          <h2 class="hero-slider__heading-text">Men’s Tees</h2>
          <p class="hero-slider__info-text">Find the perfect shirt.</p>
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
  background-position: right;
  background-size: cover;
  background-repeat: no-repeat;
}

.hero-slider__text-overlay {
  background: #efefef;
  padding: 15px;
  text-align: center;
  color: #10504f;
}

.hero-slider__heading-text {
  font-family: "Pacifico", cursive;
  font-weight: 400;
  font-size: 26px;
  margin-bottom: 10px;
}

.hero-slider__info-text {
  font-size: 14px;
  margin-top: 0;
}

.hero-slider__cta-button {
  text-decoration: none;
  padding: 15px 20px;
  background: #000;
  color: #fff;
  display: inline-block;
}

#hero-slide-1 {
  background-image: url("../assets/hero-image-1.jpg");
}

#hero-slide-2 {
  background-image: url("../assets/hero-image-2.jpg");
}

#hero-slide-3 {
  background-image: url("../assets/hero-image-3.jpg");
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
    background: none;
  }

  .hero-slider__text-overlay--desktop-white {
    color: #fff;
  }
}
</style>