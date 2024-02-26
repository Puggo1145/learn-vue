<script setup lang="ts">
import Header from './components/header.vue';
import C1Template from './components/c1_template.vue'
import C2Reactivity from './components/c2_reactivity.vue'
import C3ClassAndStyle from './components/c3_classAndStyle.vue'
import C4ConditionRendering from './components/c4_conditionRendering.vue';
import C5VForRendering from './components/c5_vForRendering.vue';
import C6HandleEvent from './components/c6_handleEvent.vue';
import C7Form from './components/c7_form.vue';
import C8LifeCycle from './components/c8_lifeCycle.vue';
import C9Watchers from './components/c9_watchers.vue';
import C10TemplateReference from './components/c10_templateReference.vue';
import C11BasicOfComponent from './components/c11_basicOfComponent.vue';
import C12ComponentVModel from './components/c12_componentVmodel.vue'

import { ref } from 'vue';

const tabs = {
  C1Template,
  C2Reactivity,
  C3ClassAndStyle,
  C4ConditionRendering,
  C5VForRendering,
  C6HandleEvent,
  C7Form,
  C8LifeCycle,
  C9Watchers,
  C10TemplateReference,
  C11BasicOfComponent,
  C12ComponentVModel
}

const currentTab = ref("C1Template");

</script>

<template>
  <Header />
  <main>
    <ul class="tab-wrapper">
      <li v-for="(_, tab) in tabs" :key="`${tab}`">
        <button @click="currentTab = tab" :class="['tab_btn', { active: currentTab === tab }]" >
          {{ tab }}
        </button>
      </li>
    </ul>
    <component :is="tabs[currentTab as keyof typeof tabs]"/>
    <!-- <C1Template />
    <C2Reactivity />
    <C3ClassAndStyle />
    <C4ConditionRendering />
    <C5VForRendering />
    <C6HandleEvent />
    <C7Form />
    <C8LifeCycle />
    <C9Watchers />
    <C10TemplateReference />
    <C11BasicOfComponent /> -->
    <div class="copywrites">
      <p>created by Puggo</p>
    </div>
  </main>
</template>

<style scoped>
main {
  padding-top: 80px;
}
.tab-wrapper {
  cursor: pointer;
  padding: 16px;
  display: flex;
  flex-wrap: wrap;
  gap: 16px
}
.copywrites {
  margin: 64px 0;
  color: #ccc;
}
.tab_btn {
  background-color: #fff;
  border: none;
  outline: none;
}
.tab_btn:hover {
  background-color: #eee;
}
.tab_btn.active {
  background-color: #eee;
} 
</style>
