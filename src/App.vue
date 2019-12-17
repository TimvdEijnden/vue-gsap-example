<template>
  <div id="app">
    <div class="controls">
      <label>Time scale:</label><br/>
      <span>10%</span>
      <input type="range" min="0.1" max="2" step="0.1" v-model.number="timeScale" />
      <span>200%</span>
    </div>
    <BoxAnimation :time-scale="timeScale"/>
    <StaggeredAnimation :time-scale="timeScale"/>
  </div>
</template>

<script>
import BoxAnimation from './components/BoxAnimation.vue'
import StaggeredAnimation from './components/StaggeredAnimation.vue'

export default {
  name: 'app',
  components: {
    BoxAnimation,
    StaggeredAnimation
  },
  data() {
    return {
      timeScale: 1
    }
  }
}
</script>

<style>
#app {
  font-family: system-ui, -apple-system;
}

.controls > * {
  vertical-align: middle;
}

label {
  font-weight: bold;
}
</style>
