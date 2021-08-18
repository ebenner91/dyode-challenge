<template>
  <footer>
    <nav class="footer__nav">
      <ul class="footer__nav-list" v-bind:class="{ active: nav1Active }">
        <li class="footer__nav-top-link" @click="nav1Active = !nav1Active">
          Customer Service
        </li>
        <li class="footer__nav-link"><a href="#">Accessibility</a></li>
        <li class="footer__nav-link"><a href="#">Contact Us</a></li>
        <li class="footer__nav-link"><a href="#">Return Policy</a></li>
        <li class="footer__nav-link"><a href="#">FAQ</a></li>
        <li class="footer__nav-link"><a href="#">Gift Certificates</a></li>
        <li class="footer__nav-link"><a href="#">Wishlist</a></li>
      </ul>
      <ul class="footer__nav-list" v-bind:class="{ active: nav2Active }">
        <li class="footer__nav-top-link" @click="nav2Active = !nav2Active">
          Company
        </li>
        <li class="footer__nav-link"><a href="#">About Us</a></li>
        <li class="footer__nav-link"><a href="#">Careers</a></li>
        <li class="footer__nav-link"><a href="#">Press</a></li>
        <li class="footer__nav-link"><a href="#">Affiliates</a></li>
      </ul>
    </nav>
    <div class="footer__social">
      <p class="footer__social-text">Follow Us</p>
      <div class="footer__social-icons">
        <a href="https://www.facebook.com" class="footer__social-icon"
          ><img
            src="../assets/facebook.svg"
            alt="Facebook Icon"
            class="footer__facebook-icon"
        /></a>
        <a href="https://www.instagram.com" class="footer__social-icon"
          ><img
            src="../assets/instagram-logo.svg"
            alt="Instagram Icon"
            class="footer__instagram-icon"
        /></a>
        <a href="https://www.twitter.com" class="footer__social-icon"
          ><img
            src="../assets/twitter.svg"
            alt="Twitter Icon"
            class="footer__twitter-icon"
        /></a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data: function () {
    return {
      nav1Active: false,
      nav2Active: false,
    };
  },
};
</script>


<style lang="scss" scoped>
footer {
  background: #000000;
  padding: 30px 20px;
}

.footer__nav {
  color: #fff;

  a {
    color: inherit;
    text-decoration: none;
  }

  .footer__nav-top-link {
    font-family: "Pacifico", cursive;
    font-size: 22px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;

    &::after {
      content: "+";
    }
  }

  .footer__nav-list {
    .footer__nav-link {
      display: none;
      font-size: 12px;
      line-height: 30px;
    }

    &.active {
      .footer__nav-top-link::after {
        content: "-";
      }

      .footer__nav-link {
        display: block;
      }
    }
  }
}

.footer__nav-list {
  list-style-type: none;
  padding: 0;
}

.footer__social-text {
  font-family: 'Pacifico', cursive;
  font-size: 22px;
  color: #fff;
}

.footer__social-icons {
  margin: 0 -15px;
}

.footer__social-icon {
  padding: 15px;
}

@media screen and (min-width: 1025px) {
  footer {
    display: flex;
    justify-content: space-between;
    padding: 60px 50px;
  }

  .footer__nav {
    display: flex;
    justify-content: space-between;

    .footer__nav-list {

      margin-right: 90px;

      .footer__nav-link {
        display: block;
        font-size: 18px;
      }

      .footer__nav-top-link::after, .footer__nav-top-link.active::after {
        content: "";
      }
    }
  }
}
</style>