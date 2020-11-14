<template>
  <div :class="menuOpen ? 'menu menu__open' : 'menu'">
    <div class="menu__content">
      <ul>
        <li><img :src="require(`~/assets/icons/home.svg`)" alt="home" /></li>
        <li>
          <img :src="require(`~/assets/icons/statistics.svg`)" alt="stats" />
        </li>
        <li>
          <img :src="require(`~/assets/icons/heart.svg`)" alt="heart.svg" />
        </li>
        <li>
          <img
            @click="toggleMenu"
            :src="
              loggedIn
                ? require(`~/assets/icons/logout.svg`)
                : require(`~/assets/icons/login.svg`)
            "
            :alt="loggedIn ? 'logout' : 'login'"
            :style="
              menuOpen
                ? 'transform: rotate(90deg); transition: 250ms ease-in-out'
                : 'transition: 250ms ease-in-out'
            "
          />
        </li>
      </ul>
    </div>
    <div v-show="menuOpen" :class="menuOpen ? 'login' : 'login login__close'">
      <div class="login__cancel" @click="toggleMenu"></div>
      <div class="login__content">
        <div class="login__content--form">
          <div>
            <img :src="require(`~/assets/icons/logo.png`)" alt="logo" />
          </div>
          <div>
            <h3>Login</h3>
          </div>
          <div>
            <p>Username</p>
            <input />
          </div>
          <div>
            <p>Password</p>
            <input type="password" />
          </div>
        </div>
        <div class="login__content--image">
          <img :src="require(`~/assets/images/3.png`)" alt="image" />
        </div>
      </div>
    </div>
    <div class="content content__menu">
      <Nuxt />
    </div>
    <div class="filter"></div>
  </div>
</template>
<script>
export default {
  name: 'MenuComponent',
  props: {
    menuOpen: {
      type: Boolean,
      default: false,
    },
    loggedIn: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    toggleMenu() {
      this.$emit('toggle-menu')
    },
  },
}
</script>
