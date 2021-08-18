<template>
  <a :href="linkUrl" class="link-card" :class="mobileWidth">
    <picture
      v-if="
        mobileWidth !== undefined && mobileWidth === 'link-card--mobile-full'
      "
    >
      <source
        media="(min-width: 799px)"
        :srcset="require(`@/assets/${desktopImageUrl}`)"
      />
      <source
        media="(min-width: 0px)"
        :srcset="require(`@/assets/${mobileImageUrl}`)"
      />
      <img :src="require(`@/assets/${mobileImageUrl}`)" :alt="imageAlt" />
    </picture>
    <img
      v-else
      :src="require(`@/assets/${desktopImageUrl}`)"
      :alt="imageAlt"
      class="link-card__image"
    />
    <p class="link-card__text"><slot></slot></p>
  </a>
</template>

<script>
export default {
  props: {
    mobileWidth: String,
    desktopImageUrl: String,
    mobileImageUrl: String,
    imageAlt: String,
    linkUrl: String,
  },
};
</script>

<style lang="scss" scoped>
.link-card {
  position: relative;
  margin-bottom: 10px;

  img {
    max-width: 100%;
    width: 100%;
  }

  .link-card__text {
    position: absolute;
    bottom: 0;
    background-color: #10504f;
    color: #fff;
    font-family: "Pacifico", cursive;
    width: 100%;
    text-align: center;
    margin: 0;
    font-size: 20px;
  }
}

.link-card--mobile-half {
  flex-basis: 49%;
}

.link-card--mobile-full {
  flex-basis: 100%;
}

@media screen and (min-width: 1025px) {
  .link-card {
    flex-basis: 32%;

    .link-card__text {
      font-size: 40px;
      padding: 20px;
    }
  }
}
</style>