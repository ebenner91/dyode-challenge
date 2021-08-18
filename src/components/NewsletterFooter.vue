<template>
  <div class="newsletter-footer">
    <h2 class="newsletter-footer__header">
      <img src="../assets/envelope.svg" alt="Envelope Icon" />{{ headerText }}
    </h2>
    <div class="newsletter-footer__content">
        <div class="newsletter-footer__text">
            <slot></slot>
        </div>
        <div class="newsletter-footer__form">
            <input class="newsletter-footer__input" placeholder="Enter Your Email Address" type="email">
            <button class="newsletter-footer__submit">Subscribe</button>
        </div>
    </div>
  </div>
</template>

<script>

export default{
    props: {
        headerText: String
    }
}
</script>
