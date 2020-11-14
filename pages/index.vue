<template>
  <div class="flex-block">
    <CardComponent title="test" :first-load="firstLoad">
      <template slot="body">
        <div
          style="
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
          "
        >
          <ProgressCircle
            :progress="progress"
            :percent="percent"
            @update-progress="updateProgress"
            color="#77709c"
            base="#908aaf40"
          />
          <ProgressCircle
            :progress="progress2"
            :percent="percent2"
            @update-progress="updateProgress"
            color="#7395bd"
            base="#8093a940"
          />
          <ProgressCircle
            :progress="progress3"
            :percent="percent3"
            @update-progress="updateProgress"
            color="#67a7a5"
            base="#899a9a40"
          />
        </div>
      </template>
    </CardComponent>
    <CardComponent title="test" />
  </div>
</template>
<script>
import CardComponent from '../components/shared/CardComponent'
import ProgressCircle from '../components/statistics/ProgressCircle'
export default {
  layout: 'default',
  components: { CardComponent, ProgressCircle },
  props: {
    firstLoad: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      progress: 314.16,
      percent: '',
      progress2: 314.16,
      percent2: '',
      progress3: 314.16,
      percent3: '',
    }
  },
  mounted() {
    this.updateProgress()
  },
  methods: {
    /* updateProgress(value) {
      this.progress = 314.16 - (value / 100) * 314.16
      this.percent = `${value}%`
    }, */
    updateProgress() {
      setTimeout(() => {
        this.progress = 314.16 - (50 / 100) * 314.16
        this.percent = `${50}%`
      }, 100),
        setTimeout(() => {
          this.progress1 = 314.16 - (23 / 100) * 314.16
          this.percent1 = `${23}%`
        }, 100),
        setTimeout(() => {
          this.progress2 = 314.16 - (79 / 100) * 314.16
          this.percent2 = `${79}%`
        }, 100),
        setTimeout(() => {
          this.progress3 = 314.16 - (40 / 100) * 314.16
          this.percent3 = `${40}%`
        }, 100)
    },
  },
}
</script>
