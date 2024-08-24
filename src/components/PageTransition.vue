<template>
    <transition name="fade" @before-enter="beforeEnter" @enter="enter" @leave="leave">
      <div v-if="show" class="transition-overlay"></div>
    </transition>
  </template>
  
  <script>
  export default {
    props: {
      show: {
        type: Boolean,
        required: true
      }
    },
    methods: {
      beforeEnter(el) {
        el.style.opacity = 0;
      },
      enter(el, done) {
        el.offsetWidth; // trigger reflow
        el.style.transition = 'opacity 0.5s';
        el.style.opacity = 1;
        done();
      },
      leave(el, done) {
        el.style.transition = 'opacity 0.5s';
        el.style.opacity = 0;
        done();
      }
    }
  }
  </script>
  
  <style scoped>
  .transition-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: black;
    opacity: 0;
    pointer-events: none; /* Optional: Makes sure the overlay does not interfere with user interactions */
  }
  </style>
  