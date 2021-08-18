<template>
  <header>
    <div class="promoBanner">{{ promoBanner }}</div>
    <div class="header-main container">
      <div class="header-main__left-content">
        <span class="header-main__nav-toggle">
          <img src="../assets/hamburger.svg" />
        </span>
        <a href="/" class="header-main__brand"
          ><img alt="Brand Logo" src="../assets/logo.png"
        /></a>
      </div>
      <nav class="header-main__nav">
        <ul class="header-main__nav-list">
          <li class="header-main__nav-link"><a href="#">Men's</a></li>
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
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    promoBanner: String,
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
}
</style>