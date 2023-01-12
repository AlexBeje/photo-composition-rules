<script setup>
import { ref } from 'vue';
import IconForward from '~icons/material-symbols/arrow-forward-ios-rounded';
const itemOpened = ref(false);

function toggleItem() {
  itemOpened.value = !itemOpened.value;
}
</script>

<template>
  <div class="container">
    <div class="top-section" @click="toggleItem">
      <div class="small-image"></div>
      <h2 class="title">Title</h2>
      <div class="icon">
        <IconForward v-if="itemOpened" class="arrow-rotated" />
        <IconForward v-else />
      </div>
    </div>
    <div class="bottom-section" v-if="itemOpened">
      <div>description</div>
      <div class="large-image">image</div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  border-radius: 8px;
  overflow: hidden;
  .top-section {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #1c1c1e;
    padding: 0.5rem 1rem;
    .small-image {
      width: 48px;
      height: 48px;
      background: #39383d;
      border-radius: 50%;
    }
    .title {
      flex: 1;
      margin: 0 1rem;
      font-weight: 400;
    }
    .icon {
      width: 48px;
      height: 48px;
      display: flex;
      justify-content: center;
      align-items: center;
      .arrow-rotated {
        transform: rotate(90deg);
      }
    }
  }
  .bottom-section {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    background: linear-gradient(
      180deg,
      rgb(18, 18, 18) 0%,
      rgba(28, 28, 28, 1) 100%
    );
  }
}
</style>
