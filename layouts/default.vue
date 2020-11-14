<template>
  <div>
    <div id="logo">
      <img :src="require(`~/assets/icons/logo.png`)" alt="logo" />
      <p>&copy; {{ new Date().getFullYear() }}</p>
    </div>
    <MenuComponent
      :menu-open="menuOpen"
      :logged-in="loggedIn"
      @toggle-menu="toggleMenu"
    />
    <div class="content" v-show="!menuOpen">
      <Nuxt />
    </div>
    <div
      class="filter__main"
      :style="
        !menuOpen && !firstLoad ? 'animation: blurIn 250ms ease-in-out' : ''
      "
    ></div>
    <div class="filter__main--background"></div>
  </div>
</template>
<script>
import MenuComponent from '@/components/shared/MenuComponent'
export default {
  data() {
    return {
      menuOpen: false,
      firstLoad: true,
    }
  },
  methods: {
    toggleMenu() {
      ;(this.firstLoad = false), (this.menuOpen = !this.menuOpen)
      console.log(this.menuOpen)
    },
  },
}
</script>
