<template>
  <div>
    <img class="runner first" src="../assets/runner.png" alt="runner">
    <img class="runner second" src="../assets/runner.png" alt="runner">
    <img class="runner third" src="../assets/runner.png" alt="runner">
  </div>
</template>

<script>
import gsap from "gsap"
export default {
  data() {
    return {

    }
  },
  mounted() {
    let tl = gsap.timeline({ repeat: -1, repeatDelay: 1 })

    tl.to('.first', { x: 200, duration: 2, ease: 'expo.out'})
    tl.to('.second', { x: 400, duration: 2, ease: 'expo.out'}, '-=1')
    tl.to('.third', { x: 600, duration: 2, ease: 'expo.out'})
  },
}
</script>
<style>
.runner {
  display: block;
  height: 5em;
  width: 5em;
  margin-top: 1.5em;
}
</style>