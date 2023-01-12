<script setup>
const test = true;
</script>

<template>
  <div class="container">
    <div class="top-section">
      <div class="small-image"></div>
      <h2 class="title">Title</h2>
      <div class="icon"></div>
    </div>
    <div class="bottom-section" v-if="test">
      <div class="large-image">image</div>
      <div>description</div>
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
    padding: 1rem;
    .small-image {
      width: 40px;
      height: 40px;
      background: #39383d;
    }
    .title {
      flex: 1;
      margin: 0 1rem;
    }
    .icon {
      width: 40px;
      height: 40px;
      background: #39383d;
    }
  }
  .bottom-section {
    background: #39383d;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    .large-image {
      background-color: red;
    }
  }
}
</style>
