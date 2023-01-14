<script setup>
import CompositionRule from './components/CompositionRule.vue';
import ScrollToTop from './components/ScrollToTop.vue';
import data from './data/compositionTechniques.json';
</script>

<template>
  <div class="app-container">
    <h1>Composition Rules</h1>
    <div class="composition-rules">
      <CompositionRule
        v-for="{ id, title, description } in data"
        :id="id"
        :title="title"
        :description="description"
        :key="id"
      />
    </div>
    <ScrollToTop />
  </div>
</template>

<style scoped lang="scss">
h1 {
  margin: 2rem 0 1rem 0;
  font-weight: 700;
}
.app-container {
  margin: 1rem;
}
.composition-rules {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
