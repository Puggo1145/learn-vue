<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
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
    <Chapter number="3" container-title="Class And Style Bind">
        <Block section-name="bind HTML class with Computed Property">
            <p :class="classObject">This text should be red if style is activated</p>
            <button @click="switchButtonStatus">Switch text status</button>
        </Block>
        <Block section-name="use array+conditional expression to render">
            <p :class="[isStyle ? isStyle : '', 'text-error']">Same Style as Block 1</p>
        </Block>
        <Block section-name="inherit property from top component to inner element">
            <C3component class="styleToInner"/>
        </Block>
    </Chapter>
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