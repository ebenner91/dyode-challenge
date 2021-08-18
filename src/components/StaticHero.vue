<template>
    <div class="static-hero__relative-container">
        <div class="static-hero__hero-content"></div>
        <div class="static-hero__text-overlay">
          <h2 class="static-hero__heading-text">Shop New Arrivals</h2>
          <p class="static-hero__info-text">
            Our coolest new items are waiting for you!
          </p>
          <a href="#" class="static-hero__cta-button">Shop Now</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.static-hero__relative-container {
    position: relative;
}

.static-hero__hero-content {
  padding: 1px;
  height: 60vw;
  background-image: url("../assets/hero-image-1.jpg");
  background-position: left;
  background-size: cover;
  background-repeat: no-repeat;
}

@media screen and (min-width: 1025px) {
  .static-hero__hero-content {
    height: 80vh;
  }

  .static-hero__text-overlay {
    position: absolute;
    top: 50%;
    left: 130px;
    transform: translateY(-50%);
  }
}
</style>