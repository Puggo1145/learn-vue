<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
import { ref } from 'vue';

const isToggledForOne = ref(true); // Block 1: true by default
const isToggledForTwo = ref(true); // Block 2: true by default
const type = ref(1); // Block 3: redner based on condition
const vShow = ref(true)
</script>

<template>
    <Chapter number="4" container-title="conditional rendering">
        <Block section-name="v-if rendering">
            <p v-if="isToggledForOne">This text is rendered</p>
            <button @click="isToggledForOne = !isToggledForOne">toggle text</button>
        </Block>
        <Block section-name="v-if-else rendering">
            <p v-if="isToggledForTwo">rendering when not toggled</p>
            <p v-else="isToggledForTwo">rendering when toggled</p>
            <button @click="isToggledForTwo = !isToggledForTwo">toggle text</button>
        </Block>
        <Block section-name="v-else-if rendering">
            <p v-if="type % 3 === 1">Mode 1</p>
            <p v-else-if="type % 3 === 2">Mode 2</p>
            <p v-else="type % 3 === 3">Mode 3</p>
            <p>(type: {{ type }})</p>
            <button @click="type++">switch mode</button>
            <button @click="type = 1">reset type number</button>
        </Block>
        <Block section-name="v-show and v-if">
            <a href="https://cn.vuejs.org/guide/essentials/conditional.html#v-if-vs-v-show">See Doc</a>
            <p>compared to v-if, v-show maintains DOM and uses CSS to display it</p>
            <p v-show="vShow">See DOM</p>
            <button @click="vShow = !vShow">{{ vShow ? 'hide' : 'show' }}</button>
        </Block>
    </Chapter>
</template>


<style scoped></style>