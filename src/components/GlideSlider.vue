<template>
  <div class="glide" ref="glide">
    <div class="glide__track" data-glide-el="track">
      <div class="glide__slides">
        <slot></slot>
      </div>
    </div>
    <div class="glide__bullets" data-glide-el="controls[nav]">
      <button class="glide__bullet" v-for="(item, index) in numberOfSlides" :data-glide-dir="'=' + index" :key='item'></button>
    </div>
  </div>
</template>

<script>
import Glide, { Swipe, Controls } from '@glidejs/glide/dist/glide.modular.esm';


export default {
  mounted(){
    this.$nextTick(() => {
      this.glide = new Glide(this.$refs.glide,{
        swipeThreshold: 30,
        dragThreshold: 30,
        gap:0,
        type: 'carousel'
      });

      this.glide.mount({ Swipe, Controls });

      this.$on('hook:beforeDestroy', () => {
        this.glide.destroy();
      });
    });

  },

  computed:{
    numberOfSlides(){
      return this.$slots.default.filter(vnode => vnode.tag !== undefined).length;
    }
  }
}
</script>

<style lang='scss'>
@import "node_modules/@glidejs/glide/src/assets/sass/glide.core";

// Optional Theme Stylesheet
@import "node_modules/@glidejs/glide/src/assets/sass/glide.theme";

.glide__bullets {
  align-items: center;
  display: flex;
  font-size: 0;
  justify-content: center;
  text-align: center;
  width:100%;
  position: absolute;
  bottom: 208px;

  @media screen and (min-width: 1025px) {
    bottom: 20px;
  }
}

.glide__bullet {
  border-radius: 50%;
  height: 8px;
  margin: 2px;
  padding: 0;
  width: 8px;
  touch-action: none;

  @media screen and (min-width: 1025px) {
    margin: 2px 4px;
  }

  &.glide__bullet--active {
    background: #fff;
  }
}


</style>