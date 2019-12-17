<template>
  <div class="letters">
    <span>h</span>
    <span>a</span>
    <span>p</span>
    <span>p</span>
    <span>y</span>
    <span>&nbsp;</span>
    <span>2</span>
    <span>0</span>
    <span>2</span>
    <span>0</span>
    <span>!</span>
  </div>
</template>

<script>
import gsap from 'gsap'

const colors = ['red', 'yellow', 'green', 'blue', 'purple']
let timeline

export default {
  props: {
      timeScale: {
          type: Number
      }
  },
  mounted() {
    const letters = [...this.$el.children]

    timeline = gsap.timeline({ repeat: -1})

    letters.forEach(l => {
      timeline.from(l, { opacity: 0, scale: .5, duration: .5 }, '-=0.15')
    })

    colors.forEach(color => {
        timeline.to(this.$el, { color, duration: 0.25 })
      })

    timeline.to(this.$el, { color: 'black', opacity: 0, scale: 2 })
  },
  watch: {
    timeScale(value) {
      timeline.timeScale(value)
    }
  }
}
</script>

<style scoped>
.letters {
  display: flex;
  justify-content: center;
  font-size: 100px;
}
</style>