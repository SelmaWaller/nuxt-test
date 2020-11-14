<template>
  <div style="display: flex; justify-content: center">
    <svg viewbox="0 0 114 114">
      <circle
        class="base"
        r="50"
        cx="57"
        cy="57"
        stroke-dashoffset="0"
        stroke-dasharray="314.16"
        :style="`stroke: ${base}`"
      ></circle>
      <circle
        class="progress"
        transform="rotate(-90 57 57)"
        :stroke-dashoffset="progress"
        :style="`stroke: ${color}`"
        stroke-dasharray="314.16"
        r="50"
        cx="57"
        cy="57"
      ></circle>
      <g class="chart-text">
        <text x="50%" y="50%" class="chart-number">{{ percent }}</text>
      </g>
    </svg>
  </div>
</template>
<script>
export default {
  name: 'ProgressCircle',
  props: {
    progress: {
      type: Number,
      default: 0,
    },
    percent: {
      type: String,
      default: '',
    },
    color: {
      type: String,
      default: '#fff',
    },
    base: {
      type: String,
      default: '#000',
    },
  },
  methods: {
    updateProgress() {
      this.$emit('update-progress')
    },
  },
}
</script>
<style lang="scss">
svg {
  height: 114px;
  width: 114px;
  padding: 10px 0;
}
circle.base {
  fill: #ffffff00;
  stroke: white;
  stroke-width: 10;
}
circle.progress {
  fill: transparent;
  stroke-width: 10;
  stroke-linecap: round;
  transition: stroke-dashoffset 1s ease;
}
.chart-number {
  font-size: 26px;
  font-family: 'Roboto', sans-serif;
  transform: translateY(10px) translateX(-22px);
}
</style>
