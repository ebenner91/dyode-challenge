<template>
  <header>
    <div class="promoBanner">{{ promoBanner }}</div>
    <div class="header-main container">
      <div class="header-main__left-content">
        <span class="header-main__nav-toggle" @click="navActive = true">
          <img src="../assets/hamburger.svg" />
        </span>
        <a href="/" class="header-main__brand"
          ><img alt="Brand Logo" src="../assets/logo.png"
        /></a>
      </div>
      <nav class="header-main__nav">
        <ul class="header-main__nav-list">
          <li class="header-main__nav-link" @mouseenter="navActive = true"><a href="#">Men's</a></li>
          <li class="header-main__nav-link"><a href="#">Women's</a></li>
          <li class="header-main__nav-link"><a href="#">Accessories</a></li>
          <li class="header-main__nav-link"><a href="#">Sale!</a></li>
        </ul>
      </nav>
      <div class="header-main__right-content">
        <span class="header-main__search-toggle"
          ><img src="../assets/search.png" alt="Search Icon"
        /></span>
        <a href="#" class="header-main__account-link"
          ><img src="../assets/user.png" alt="User Icon"
        /></a>
        <a href="#" class="header-main__cart-link"
          ><img src="../assets/shopping-cart.png" alt="Shopping Cart Icon"
        /></a>
      </div>
      <div class="header-main__nav-popup" @mouseleave="navActive = false" v-bind:class="{ active: navActive }">
        <div class="nav-popup__top-bar">
          <img
            src="../assets/iconmonstr-x-mark-circle-thin.svg"
            alt="X in circle icon"
            class="nav-popup__exit"
            @click="navActive = false"
          />
        </div>
        <ul
          class="nav-popup__nav-list"
          v-bind:class="{ active: popupNav1Active }"
        >
          <li
            class="nav-popup__list-title"
            @click="popupNav1Active = !popupNav1Active"
          >
            Tops
          </li>
          <li class="nav-popup__nav-link"><a href="#">T-Shirts</a></li>
          <li class="nav-popup__nav-link"><a href="#">Short Sleeve</a></li>
          <li class="nav-popup__nav-link"><a href="#">Long Sleeve</a></li>
        </ul>
        <ul
          class="nav-popup__nav-list"
          v-bind:class="{ active: popupNav2Active }"
        >
          <li
            class="nav-popup__list-title"
            @click="popupNav2Active = !popupNav2Active"
          >
            Bottoms
          </li>
          <li class="nav-popup__nav-link"><a href="#">Shorts</a></li>
          <li class="nav-popup__nav-link"><a href="#">Pants</a></li>
        </ul>
        <div class="nav-popup__featured-nav">
          <img
            src="../assets/social-1.jpg"
            alt="Man wearing t-shirt"
            class="nav-popup-featured-image"
          />
          <ul class="nav-popup__featured-list">
            <li class="nav-popup__featured-link"><a href="#">Shop All</a></li>
            <li class="nav-popup__featured-link">
              <a href="#">New Arrivals</a>
            </li>
            <li class="nav-popup__featured-link"><a href="#">Favorites</a></li>
            <li class="nav-popup__featured-link"><a href="#">Sale</a></li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import "@fortawesome/fontawesome-free/css/all.css";

export default {
  name: "Header",
  props: {
    promoBanner: String,
  },
  data: function () {
    return {
      navActive: false,
      searchActive: false,
      popupNav1Active: false,
      popupNav2Active: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.promoBanner {
  background: #000;
  color: #fff;
  text-align: center;
  text-transform: uppercase;
  padding: 15px;
}

.header-main {
  background: #10504f;
  padding-top: 18px;
  padding-bottom: 18px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header-main__left-content,
.header-main__right-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header-main__right-content {
  margin: 0 -10px;
  span,
  a {
    padding: 0 10px;
    cursor: pointer;
  }
}

.header-main__nav-toggle {
  margin-right: 25px;
}

.header-main__nav {
  display: none;
}

.header-main__nav-list {
  list-style-type: none;
  padding: 0;

  .header-main__nav-link a {
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
  }
}

.header-main__nav-popup {
  display: none;
  position: fixed;
  top: 0;
  width: 80%;
  height: 100vh;
  bottom: 0;
  left: 0;
  background: #fff;
  z-index: 10;
  overflow-y: auto;

  &.active {
    display: block;
  }
}

.nav-popup__top-bar {
  padding: 15px;
  text-align: right;
  border-bottom: 0.5px solid #f1f1ef;
}

.nav-popup__nav-list {
  padding: 20px 35px;
  border-bottom: 0.5px solid #f1f1ef;
  list-style-type: none;

  .nav-popup__nav-link {
    line-height: 2.1;
    font-size: 18px;
    display: none;

    a {
      color: inherit;
      text-decoration: none;
    }
  }

  &.active {
    .nav-popup__list-title {
      &::after {
        content: "\f078";
      }
    }

    .nav-popup__nav-link {
      display: block;
    }
  }
}

.nav-popup__list-title {
  font-weight: 300;
  font-size: 16px;
  line-height: 2.8;
  text-transform: uppercase;
  display: flex;
  justify-content: space-between;
  align-items: center;

  &::after {
    content: "\f077";
    font-family: "Font Awesome 5 Free";
    font-weight: 900;
  }
}

.nav-popup__featured-nav {
  padding: 0 25px;
  margin-top: 105px;
  width: 100%;
  background: #efefef;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-popup-featured-image {
  max-width: 129px;
  height: auto;
}

.nav-popup__featured-list {
  list-style-type: none;
  padding: 0;
}

.nav-popup__featured-link {
  font-size: 18px;
  line-height: 2.1;

  a {
    text-decoration: none;
    color: inherit;
  }
}

@media screen and (min-width: 1025px) {
  .header-main__nav-toggle {
    display: none;
  }

  .header-main__nav {
    display: block;
  }

  .header-main__nav-list {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .header-main__nav-link {
    padding: 10px;
    border-bottom: 2px solid transparent;
  }

  .header-main__nav-link:hover {
    border-bottom: 2px solid #fff;
  }

  .header-main__nav-popup {
    position: absolute;
    top: 167px;
    width: 68%;
    height: unset;
    bottom: unset;
    left: unset;
    left: 50%;
    transform: translateX(-50%);

    &.active {
      display: flex;
    }
  }

  .nav-popup__top-bar {
    display: none;
  }

  .nav-popup__nav-list {
    .nav-popup__nav-link {
      display: block;
      font-size: 22px;
      line-height: 1.8;
    }
  }

  .nav-popup__list-title {
    line-height: 1.2;
    margin-bottom: 14px;
    &::after {
      content: "";
    }
  }

  .nav-popup__featured-nav {
    margin-top: 0;
    order: -1;
    padding: 45px;
    align-items: flex-start;
    width: auto;
  }

  .nav-popup__featured-list {
    margin: 0;
  }

  .nav-popup-featured-image {
    max-width: 248px;
    height: auto;
    margin-right: 60px;
  }

  .nav-popup__featured-link {
    font-size: 22px;
    line-height: 1.8;
} 
}
</style>