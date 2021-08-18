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
        <input
          class="newsletter-footer__input"
          placeholder="Enter Your Email Address"
          type="email"
        />
        <button class="newsletter-footer__submit">Subscribe</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    headerText: String,
  },
};
</script>

<style lang="scss" scoped>
.newsletter-footer {
  background: #10504f;
  color: #fff;
  padding: 25px;
}

.newsletter-footer__header {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  font-family: 'Pacifico', sans-serif;
  font-weight: 400;

  img {
    margin-right: 10px;
    max-width: 30px;
    height: auto;
  }
}

.newsletter-footer__content {
  display: flex;
  flex-wrap: wrap;
}

.newsletter-footer__text,
.newsletter-footer__form {
  flex-basis: 100%;
}

.newsletter-footer__form {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.newsletter-footer__text {
  text-align: center;
  font-size: 14px;
}

.newsletter-footer__input {
  height: 42px;
  width: 100%;
  padding-top: 8px;
  padding-left: 15px;
  margin-bottom: 55px;

  &::placeholder {
    color: #C6C6C6;
    font-size: 22px;
  }
}

.newsletter-footer__submit {
  width: 150px;
  border: 1px solid #fff;
  background: none;
  color: #fff;
  font-size: 12px;
  text-transform: uppercase;
  padding: 13px 30px;
}

@media screen and (min-width: 1025px) {
  .newsletter-footer {
    padding: 50px 100px;
  }

  .newsletter-footer__header {
    font-size: 40px;

    img {
      max-width: none;
    }
  }

  .newsletter-footer__text,
  .newsletter-footer__form {
    flex-basis: 49%;
  }

  .newsletter-footer__form {
    display: flex;
    align-items: center;
  }

  .newsletter-footer__text {
    text-align: left;
    font-size: 22px;
  }

  .newsletter-footer__input {
    width: calc(100% - 140px);
    height: 56px;
    margin-bottom: 0;
  }

  .newsletter-footer__submit {
  width: 140px;
  padding: 20px 30px;
}
}
</style>
