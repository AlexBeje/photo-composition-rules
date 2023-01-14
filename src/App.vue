<script setup>
import CompositionRule from './components/CompositionRule.vue';
import data from './data/compositionTechniques.json';
</script>

<template>
  <div class="app-container">
    <h1>Composition Rules</h1>
    <div class="composition-rules">
      <CompositionRule
        v-for="{ id, title, src, description } in data"
        :title="title"
        :src="src"
        :description="description"
        :key="id"
      />
    </div>
  </div>
</template>

<style scoped>
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
