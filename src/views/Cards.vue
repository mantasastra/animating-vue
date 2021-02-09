<template>
  <div>
    <transition-group
      appear
      @before-enter="beforeEnter"
      @enter="enter"
      :css="false"
    >
      <div class="card" v-for="card in cards" :key="card.id">
        <p>{{ card.title }}</p>
      </div>
    </transition-group>
  </div>
</template>

<script>
import Velocity from 'velocity-animate'

export default {
  name: 'Cards',
  data() {
    return {
      cards: [
        { title: "Harry Potter and the Philosopher's stone", id: 1 },
        { title: 'Harry Potter and the Chamber of Secrets', id: 2 },
        { title: 'Harry Potter and the Prisoner of Azkaban', id: 3 },
        { title: 'Harry Potter and the Goblet of Fire', id: 4 },
        { title: 'Harry Potter and the Order of the Phoenix', id: 5 },
        { title: 'Harry Potter and the Half-Blood Prince', id: 6 },
        { title: 'Harry Potter and the Deathly Hallows', id: 7 },
      ],
    }
  },
  methods: {
    beforeEnter(el) {
      el.style.opacity = 0
      el.style.width = '0em'
    },
    enter(el, done) {
      Velocity(
        el,
        { opacity: 1, width: '12em', rotateZ: '3deg' },
        { duration: 1000, easing: [70, 8], complete: done }
      )
    },
  },
}
</script>

<style scoped>
.card {
  height: 4em;
  width: 12em;
  border-radius: 1%;
  background-color: #e0e0e0;
  box-shadow: 0.08em 0.03em 0.4em #ababab;
  padding: 1rem;
}
</style>
