<template>
  <div
    class="card"
    :style="
      !menuOpen && !firstLoad ? 'animation: blurIn 250ms ease-in-out' : ''
    "
  >
    <h2>{{ title }}</h2>
    <slot name="body"></slot>
  </div>
</template>
<script>
export default {
  layout: 'default',
  props: {
    title: {
      type: String,
      default: 'Title',
    },
    firstLoad: {
      type: Boolean,
      default: true,
    },
  },
}
</script>
