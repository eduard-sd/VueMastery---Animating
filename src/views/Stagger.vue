<template>
  <div>
    <div class="container">
      <div class="box" v-for="z in cards" :key="z.id"></div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap"
export default {
  data() {
    return {
      cards: [
        { id: 1298 },
        { id: 1299 },
        { id: 1289 },
        { id: 1288 },
        { id: 1277 },
        { id: 1266 },
      ]
    }
  },
  mounted() {
    gsap.from('.box', {
      duration: 0.5,
      opacity: 0,
      scale: 0,
      y: 200,
      ease: 'power1',
      // stagger: 0.1 //delay between each box
      stagger: {
        each: 0.1,
        // from: 'edges'
        from: 'center'
      }
    })
  }
}
</script>
<style>
.container {
  display: flex;
  flex-wrap: wrap;
}

.box {
  display: block;
  margin: 0 auto 0 auto;
  height: 6.5em;
  width: 6.5em;
  border-radius: 1%;
  background-color: #16c0b0;
  box-shadow: 0.08em 0.03em 0.4em #ababab;
}
</style>