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
            @click="menuOpen = !menuOpen"
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
    <div
      :class="menuOpen ? 'login' : 'login login__close'"
      :style="
        !menuOpen
          ? 'animation: closeMenu 250ms ease-in-out;'
          : 'animation: openMenu 250ms ease-in-out;'
      "
    >
      <div class="login__form">
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
          <input />
        </div>
      </div>
    </div>
    <div class="filter"></div>
  </div>
</template>
<script>
export default {
  name: 'MenuComponent',
  data: () => ({
    menuOpen: true,
    loggedIn: false,
  }),
}
</script>
