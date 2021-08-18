<template>
    <div class="static-hero__relative-container">
        <div class="static-hero__hero-content"></div>
        <div class="static-hero__text-overlay">
          <h2 class="static-hero__heading-text">Our Favorite Tees</h2>
          <p class="static-hero__info-text">
            Everyday tees you need
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
  background-image: url("../assets/static-hero-image.jpg");
  background-position: left;
  background-size: cover;
  background-repeat: no-repeat;
}

.static-hero__text-overlay {
  background: #EFEFEF;
  padding: 15px;
  text-align: center;
  color: #10504f;
}

.static-hero__heading-text {
  font-family: 'Pacifico', cursive;
  font-weight: 400;
  font-size: 26px;
  margin-bottom: 10px;
}

.static-hero__info-text {
  font-size: 14px;
  margin-top: 0;
}

.static-hero__cta-button {
  text-decoration: none;
  padding: 15px 20px;
  background: #000;
  color: #fff;
  display: inline-block;
}

@media screen and (min-width: 1025px) {
  .static-hero__hero-content {
    height: 100vh;
  }

  .static-hero__text-overlay {
    position: absolute;
    top: 50px;
    right: 50px;
    background: none;
    color: #fff;
    text-align: left;
  }

  .static-hero__heading-text {
    font-size: 60px;
  }

  .static-hero__cta-button {
    background: #10504f;
  }

}
</style>