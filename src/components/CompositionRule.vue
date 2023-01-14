<script setup>
import { ref } from 'vue';
import IconForward from '~icons/material-symbols/arrow-forward-ios-rounded';

defineProps({
  title: String,
  src: String,
  description: String,
});

const itemOpened = ref(false);

function toggleItem() {
  itemOpened.value = !itemOpened.value;
}
</script>

<template>
  <div class="container">
    <div class="top-section" @click="toggleItem">
      <img class="small-image" :src="src" />
      <h4 class="title">{{ title }}</h4>
      <div class="icon">
        <IconForward v-if="itemOpened" class="arrow-rotated" />
        <IconForward v-else />
      </div>
    </div>
    <div class="bottom-section" v-if="itemOpened">
      <img class="large-image" :src="src" />
      <span v-html="description" />
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
    cursor: pointer;
    .small-image {
      width: 48px;
      height: 48px;
      background: #39383d;
      border-radius: 50%;
      background-size: auto;
      object-fit: cover;
    }
    .title {
      flex: 1;
      margin: 0 1rem;
      font-weight: 700;
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
    background: linear-gradient(
      180deg,
      rgb(18, 18, 18) 0%,
      rgba(28, 28, 28, 1) 100%
    );
    .large-image {
      border-radius: 4px;
      margin-bottom: 1rem;
    }
  }
}
</style>
