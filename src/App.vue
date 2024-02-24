<script setup lang="ts">
import Header from './components/header.vue';
import C1Template from './components/c1_template.vue'
import C2Reactivity from './components/c2_reactivity.vue'
</script>

<template>
  <Header />
  <C1Template />
  <C2Reactivity />
  <div class="copywrites">
    <p>created by Puggo</p>
  </div>
</template>

<style scoped>
.copywrites {
  margin: 64px 0;
  color: #ccc;
}
</style>
