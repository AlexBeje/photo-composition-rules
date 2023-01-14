<script setup>
import { ref } from 'vue';

import IconForward from '~icons/material-symbols/arrow-forward-ios-rounded';

const pageTop = ref(0);

function handleScroll() {
  pageTop.value = window.visualViewport.pageTop;
}

window.addEventListener('scroll', handleScroll);

function scrollToTop() {
  window.scrollTo(0, 0);
}
</script>

<template>
  <button class="scroll-to-top" @click="scrollToTop" v-if="pageTop > 250">
    <IconForward class="arrow-rotated" />
  </button>
</template>

<style scoped lang="scss">
.scroll-to-top {
  cursor: pointer;
  position: fixed;
  bottom: 4rem;
  right: 4rem;
  width: 5rem;
  height: 5rem;
  background: white;
  border: none;
  border-radius: 4px;
  .arrow-rotated {
    transform: rotate(-90deg);
    color: black;
    font-size: 2rem;
  }
}
</style>
