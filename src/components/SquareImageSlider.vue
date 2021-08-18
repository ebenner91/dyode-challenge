<template>
  <div class="square-image-slider">
    <h2 class="square-image-slider__title">{{ title }}</h2>
    <div class="glide" ref="glide">
      <div class="glide__track" data-glide-el="track">
        <div class="glide__slides">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Glide, {
  Swipe,
  Breakpoints,
  Autoplay,
} from "@glidejs/glide/dist/glide.modular.esm";

export default {
  mounted() {
    this.$nextTick(() => {
      this.glide = new Glide(this.$refs.glide, {
        swipeThreshold: 30,
        dragThreshold: 30,
        gap: 20,
        type: "carousel",
        perView: 5,
        focusAt: "center",
        autoplay: 2500,
        hoverpause: true,
        breakpoints: {
          1024: {
            perView: 3,
            gap: 10,
          },
        },
      });

      this.glide.mount({ Swipe, Breakpoints, Autoplay });

      this.$on("hook:beforeDestroy", () => {
        this.glide.destroy();
      });
    });
  },
  props: {
    title: String,
  },
};
</script>

<style scoped>
.square-image-slider__title {
  text-align: center;
  font-weight: 400;
  font-size: 26px;
  font-family: "Pacifico", cursive;
}

@media screen and (min-width: 1025px) {
  .square-image-slider__title {
    font-size: 60px;
    margin-bottom: 35px;
  }
}
</style>