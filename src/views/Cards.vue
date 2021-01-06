<template>
  <div class="list">
    <button @click="isOpen = !isOpen">Show cards</button>
    <transition
        @before-enter="beforeEnter"
        @enter="enter"
        @leave="leave"
        :css="false"
    >
      <div v-if="isOpen" class="cards">
        <div v-for="card in cardsTitles" :key="card" class="card">
          {{ card }}
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import Velocity from 'velocity-animate'

export default {
  data() {
    return {
      isOpen: false,
      cardsTitles: ['Fast Food', 'Healthy Food']
    };
  },
  methods: {
    beforeEnter(el) {
      el.style.opacity = 0
      el.style.width = '0em'
    },
    enter(el, done) {
      Velocity(
          el,
          { opacity: 1, width: '12em' },
          { duration: 500, easing: [100, 10], complete: done }
      )
    },
    leave(el, done) {
      Velocity(
          el,
          { opacity: 0, width: '0em' },
          { duration: 500, easing: [90, 10], complete: done }
      )
    }
  }
}
</script>

<style>
  .cards {
    display: flex;
    flex-direction: column;
  }

  .card {
    height: 3.5em;
    width: 95%;
    margin-top: 0.6em;
    background-color: #f0f0f0;
    border: 0.02em solid #ababab;
    border-radius: 10px;
    transform: rotate(5deg);
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>