<template>
  <div class="product-slider">
    <h2 class="product-slider__header">New Arrivals</h2>
    <div class="glide" ref="glide">
      <div class="glide__arrows" data-glide-el="controls">
        <button class="glide__arrow glide__arrow--left" data-glide-dir="<">
          <img src="../assets/left-arrow.svg" alt="Left Arrow" />
        </button>
      </div>
      <div class="glide__track" data-glide-el="track">
        <div class="glide__slides">
          <slot></slot>
        </div>
      </div>
      <div class="glide__arrows" data-glide-el="controls">
        <button class="glide__arrow glide__arrow--right" data-glide-dir=">">
          <img src="../assets/right-arrow.svg" alt="Right Arrow" />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import Glide, {
  Swipe,
  Controls,
  Breakpoints,
} from "@glidejs/glide/dist/glide.modular.esm";

export default {
  mounted() {
    this.$nextTick(() => {
      this.glide = new Glide(this.$refs.glide, {
        swipeThreshold: 30,
        dragThreshold: 30,
        gap: 20,
        type: "carousel",
        perView: 4,
        breakpoints: {
          1024: {
            perView: 2,
            gap: 10,
          },
        },
      });

      this.glide.mount({ Swipe, Controls, Breakpoints });

      this.$on("hook:beforeDestroy", () => {
        this.glide.destroy();
      });
    });
  },
};
</script>

<style lang="scss" scoped>

.product-slider__header {
  text-align: center;
  font-family: 'Pacifico', cursive;
  font-size: 26px;
  font-weight: 400;
}
.glide {
  display: flex;
  align-items: center;
  padding: 0 20px;
}

.glide__track {
  flex: 1;
}

.glide__arrow {
  position: relative;
  top: 0;
  margin: 0;
  transform: none;
  left: 0;
  right: 0;
  padding: 0;
  border: none;
  box-shadow: none;
  background: none;
}

@media screen and (min-width: 1025px) {
  .product-slider__header {
    font-size: 60px;
  }
}
</style>
