<template>
  <div>
    <div id="logo">
      <img :src="require(`~/assets/icons/logo.png`)" alt="logo" />
      <p>&copy; {{ new Date().getFullYear() }}</p>
    </div>
    <MenuComponent />
    <Nuxt />
  </div>
</template>
<script>
import MenuComponent from '@/components/shared/MenuComponent'
export default {}
</script>
