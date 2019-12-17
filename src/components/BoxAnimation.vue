<template>
    <div class="box">

    </div>
</template>

<script>
import gsap from "gsap";

let timeline

export default {
  props: {
    timeScale: {
      type: Number
    }
  },
  mounted: function() {
    timeline = gsap.timeline({ repeat: -1, repeatDelay: 1, yoyo: true });
    timeline.to(this.$el, { rotation: -90, duration: 2, ease: "back" });
    timeline.to(this.$el, { duration: 0.5, backgroundColor: "yellow" }, "-=1");
  },
  watch: {
    timeScale(value) {
      timeline.timeScale(value)
    }
  }
};
</script>

<style scoped>
.box {
  background: green;
  width: 200px;
  height: 200px;
  margin: 0 auto;
}
</style>