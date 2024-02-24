<script setup lang="ts">
import { ref } from 'vue';

type standardObjStructure = Record<string, string | number> 

const count = ref(0);
const isBtnDisabled = ref(false);
const visibility = ref(true);
const eventName = ref('mouseover');
const bindMultiAttributes: standardObjStructure = {
  class: "bindInstanceClass",
  id: "bindInstanceId"
}
const deepTrackOfRef: standardObjStructure= {
  number: 0
}

const increment = () => {
  count.value++;
}

const changeEvent = () => {
  console.log('change');
  
  return eventName.value = eventName.value === 'mouseover' ? 'click' : 'mouseover';
}
</script>

<template>
  <h1>Chapter1 - template</h1>
  <div class="main-container">
    <section class="counter">
      <h4>counter</h4>
      <h1>{{ count }}</h1>
      <button @click="increment">increase the number of count</button>
    </section>
    <section class="binder">
      <h4>v-bind:disabled</h4>
      <button :disabled="isBtnDisabled" @click="console.log(isBtnDisabled)">button under control</button>
      <button @click="isBtnDisabled = !isBtnDisabled">change button usability</button>
    </section>
    <section class="AttributesBinder">
      <h4>multi-attributes (open console)</h4>
      <p v-bind="bindMultiAttributes">This tag binds multiple attributes</p>
    </section>
    <section class="vIf">
      <h4>v-if</h4>
      <p v-if="visibility">This text is visible</p>
      <button @click="visibility = !visibility">change visibility</button>
    </section>
    <section class="dynamicAttributes">
      <h4>v-bind:[attributeName]</h4>
      <p>current: {{ eventName }}</p>
      <button @[eventName]="changeEvent">changeEvent</button>
    </section>
    <section class="deepTrackOfRef">
      <h4>v-bind:[attributeName]</h4>
      <p>{{ deepTrackOfRef.number }}</p>
      <button>change number in an object</button>
    </section>
  </div>
</template>

<style>
.main-container {
  width: 864px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.main-container section {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 16px;
  border-radius: 8px;
  background-color: #eee;
}

section:nth-child(3n) {
  flex: 1;
}
</style>