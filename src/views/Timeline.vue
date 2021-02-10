<template>
  <div>
    <img class="runner first" src="../assets/avatar.png" alt="runner" />
    <img class="runner second" src="../assets/avatar.png" alt="runner" />
    <img class="runner third" src="../assets/avatar.png" alt="runner" />
  </div>
</template>

<script>
import gsap from 'gsap'

export default {
  mounted() {
    let tl = gsap.timeline({ repeat: -1 })
    tl.to('.first', {
      x: 700,
      duration: 2,
      ease: 'expo.out',
    })
    tl.to(
      '.second',
      {
        x: 700,
        duration: 2,
        ease: 'expo.out',
      },
      '<'
    )
    tl.to('.third', {
      x: 700,
      duration: 2,
      ease: 'expo.out',
    })
  },
}
</script>

<style scoped>
.runner {
  display: block;
  height: 5em;
  width: 5em;
  margin-top: 1.5em;
}
</style>
