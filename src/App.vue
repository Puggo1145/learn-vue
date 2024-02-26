<script setup lang="ts">
import Header from './components/header.vue';
import C1Template from './components/c1_template.vue'
import C2Reactivity from './components/c2_reactivity.vue'
import C3ClassAndStyle from './components/c3_classAndStyle.vue'
import C4ConditionRendering from './components/c4_conditionRendering.vue';
import C5VForRendering from './components/c5_vForRendering.vue';
import C6HandleEvent from './components/c6_handleEvent.vue';
</script>

<template>
  <Header />
  <C1Template />
  <C2Reactivity />
  <C3ClassAndStyle />
  <C4ConditionRendering />
  <C5VForRendering />
  <C6HandleEvent />
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
