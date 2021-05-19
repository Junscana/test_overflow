<template>
  <header class="header">
    <div class="header__inner">
      <!-- <div class="header__logo">
        <nuxt-link :to="logo.url" class="footer__logo__inner">
          <img :src="logo.src" :alt="logo.alt">
        </nuxt-link>
      </div> -->
      <div
        class="header__menu-btn"
        :class="{ active: menuBtnActive }"
        @click="menuBtnActive = !menuBtnActive"
      />
    </div>
    <div
      class="header__menu-layer"
      :class="{ active: menuBtnActive }"
      @click="menuBtnActive = !menuBtnActive"
    />
    <div
      class="header__menu"
      :class="{ active: menuBtnActive }"
    >
      <ul class="header__menu__inner">
        <li v-for="(menuItem, menuIndex) in menuList" :key="`menu-${menuIndex}`" class="header__menu__inner__item" @click="menuBtnActive = !menuBtnActive">
          <nuxt-link :to="menuItem.url" class="header__menu__inner__item__inner fontUppercase" :target="menuItem.isBlank">
            {{ menuItem.text }}
          </nuxt-link>
        </li>
        <li v-for="(menuItem, menuExtraIndex) in menuListExtraLink" :key="`menuExtra-${menuExtraIndex}`" class="header__menu__inner__item">
          <!-- <a :href="menuItem.url" class="header__menu__inner__item__inner fontUppercase" target="_blank"> -->
          <span class="header__menu__inner__item__inner fontUppercase">
            {{ menuItem.text }}
          </span>
          <!-- </a> -->
          <p class="font-s fontUppercase" style="color: #707070; font-size: 1.4rem;">※online shopは現在準備中です</p>
        </li>
        <!-- <li v-for="(menuItem, index) in menuListExtraLink" :key="index" class="header__menu__inner__item" @click="menuBtnActive = !menuBtnActive">
          <a :href="menuItem.url" class="header__menu__inner__item__inner fontUppercase" target="_blank">
            {{ menuItem.text }}
          </a>
        </li> -->
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: 'LayoutHeader',
  data () {
    return {
      menuBtnActive: false,
      logo: {
        url: '/',
        src: require('~/assets/images/logo/logo-pink.png'),
        alt: 'OVERFLOWのロゴ'
      },
      menuList: [
        {
          text: 'home',
          url: '/',
          isBlank: 'false'
        },
        {
          text: 'news',
          url: '/news/',
          isBlank: 'false'
        },
        {
          text: 'about',
          url: '/about/',
          isBlank: 'false'
        },
        {
          text: 'profile',
          url: '/profile/',
          isBlank: 'false'
        },
        {
          text: 'schedule',
          url: '/schedule/',
          isBlank: 'false'
        },
        {
          text: 'discography',
          url: '/discography/',
          isBlank: 'false'
        },
        {
          text: 'faq',
          url: '/faq/',
          isBlank: 'false'
        },
        {
          text: 'contact',
          url: '/contact/',
          isBlank: 'false'
        }
      ],
      menuListExtraLink: [
        {
          text: 'online shop',
          url: 'http://ssuggoi.net/'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.header {
  height: 6.4rem;
  width: 100%;
  padding: 1.5rem;
  box-sizing: border-box;
  // background: rgb(255,255,255);
  // background: linear-gradient(90deg, rgba(255,255,255,1) 0%, rgba(255,245,255,1) 100%);
  background: linear-gradient(90deg, rgba(255,255,255,0) 0%, rgba(174, 216, 255, 0) 100%);
  position: fixed;
  top: 0;
  z-index: 1;
  transition-duration: 0.4s;

  &__inner {
    display: flex;
    align-items: center;
    // justify-content: space-between;
    justify-content: flex-end;
  }

  &__logo {
    // width: 15rem;
    height: 3.4rem;

    &__inner {
      height: 100%;
    }

    img {
      height: 100%;
      width: auto;
    }
  }

  &__menu-btn {
    height: 3.4rem;
    width: 3.4rem;
    position: relative;
    z-index: 11;

    &::before {
      content: "";
      display: inline-block;
      height: 1px;
      width: 3.6rem;
      background-color: #000;
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      margin: auto;
      transform: translateY(-0.8rem);
      transition-duration: 0.4s;
    }

    &::after {
      content: "";
      display: inline-block;
      height: 1px;
      width: 3.6rem;
      background-color: #000;
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      margin: auto;
      transform: translateY(0.8rem);
      transition-duration: 0.4s;
    }
  }

  &__menu-btn.active {
    &::before {
      background-color: #f2c0d6;
    }

    &::after {
      background-color: #f2c0d6;
    }
  }

  // ヘッダーメニュー活性ここから
  &__menu-btn.active {
    &::before {
      transform: rotate(45deg);
    }

    &::after {
      transform: rotate(-45deg);
    }
  }
  // ヘッダーメニュー活性ここまで

  &.colored {
    background: linear-gradient(90deg, rgba(255,255,255,0.6) 0%, rgba(174, 216, 255, 0.6) 100%);
    // opacity: 0.6;
    transition-duration: 0.4s;
  }
}

.header__menu {
  height: 100%;
  width: 60%;
  padding: 6.4rem 1.5rem 0;
  // background-color: rgb(255, 228, 254); // del
  background-color: rgba(255, 255, 255, 1);
  position: fixed;
  top: 0;
  right: -80%;
  z-index: 10;
  transition-duration: 0.6s;

  &__inner {
    width: 15rem;
    margin: auto;
  }

  &__inner__item__inner {
    padding: 1rem 0;
    display: block;
    color: #F2C0D6;
  }
}

.header__menu-layer {
  height: 100%;
  width: 100%;
  position: fixed;
  top: 0;
  left: -100%;
  z-index: 9;
  background-color: rgba(0, 0, 0, 0.2);
  transition-duration: 0.6s;
  animation-delay: 2s;
}

.header__menu-layer.active {
  left: 0;
  transition-duration: 0.6s;
  animation-delay: 2s;
}

.header__menu.active {
  right: 0;
}

@media screen and (min-width: 768px) {
  .header__inner {
    max-width: 100rem;
    margin: auto;
  }
}
</style>
