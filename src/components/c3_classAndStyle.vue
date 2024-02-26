<script setup lang="ts">
import { ref, computed } from 'vue';
import C3component from './innerComponent/C3component.vue'
const isStyle = ref(true);
const error = ref(false);

const classObject = computed(() => ({
    'isStyle': isStyle.value && !error.value,
    'text-error': error.value
}))

const switchButtonStatus = () => {
    error.value = !error.value;
}
</script>

<template>
    <h1>Chapter 3 - Class And Style Bind</h1>
    <div class="main-container">
        <section class="bindClassAndStyle">
            <h4>bind HTML class with Computed Property</h4>
            <p :class="classObject">This text should be red if style is activated</p>
            <button @click="switchButtonStatus">Switch text status</button>
        </section>
        <section class="useArrayToRender">
            <h4>use array+conditional expression to render</h4>
            <p :class="[isStyle ? isStyle : '', 'text-error']">Same Style as section 1</p>
        </section>
        <section class="relationOfComponentAndTopElementClass">
            <h4>inherit property from top component to inner element</h4>
            <C3component class="styleToInner"/>
        </section>
    </div>
</template>


<style scoped>
.hasStyle {
    color: '#4599df';
}
.text-error {
    color: red;
    font-weight: 800;
}
.useArrayToRender {
    flex: 1
}
.styleToInner {
    display: flex;
    flex-direction: column;
    background-color: #eee;
    border-radius: 4px;
}
</style>