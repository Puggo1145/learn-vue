<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
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
  <Chapter number="1" container-title="template">
    <Block section-name="counter">
      <h1>{{ count }}</h1>
      <button @click="increment">increase the number of count</button>
    </Block>
    <Block section-name="v-bind:disabled">
      <button :disabled="isBtnDisabled" @click="console.log(isBtnDisabled)">button under control</button>
      <button @click="isBtnDisabled = !isBtnDisabled">change button usability</button>
    </Block>
    <Block section-name="multi-attributes (open console)">
      <p v-bind="bindMultiAttributes">This tag binds multiple attributes</p>
    </Block>
    <Block section-name="v-if">
      <p v-if="visibility">This text is visible</p>
      <button @click="visibility = !visibility">change visibility</button>
    </Block>
    <Block section-name="v-bind:[attributeName]">
      <p>current: {{ eventName }}</p>
      <button @[eventName]="changeEvent">changeEvent</button>
    </Block>
    <Block section-name="v-bind:[attributeName]">
      <p>{{ deepTrackOfRef.number }}</p>
      <button>change number in an object</button>
    </Block>
  </Chapter>
</template>

<style>

</style>