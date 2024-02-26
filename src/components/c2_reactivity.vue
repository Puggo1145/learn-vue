<script lang="ts" setup>
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
import { ref, shallowRef } from 'vue';

const deepTrackObject = ref({
    number: 0
});
const shallowTrackOfRef = shallowRef({
    number: 0
});
</script>

<template>
    <Chapter number="2" container-title="reactivity">
        <Block section-name="deep track of Ref">
            <p>number in an object: {{ deepTrackObject.number }}</p>
            <button @click="deepTrackObject.number++">increase number</button>
        </Block>
        <Block section-name="shallow Ref">
            <span>the change of number won't trigger update</span>
            <span>but the value will update and represented in next update</span>
            <p>number in an object: {{ shallowTrackOfRef.number }}</p>
            <button @click="shallowTrackOfRef.number++">increase number</button>
        </Block>
    </Chapter>
</template>

<style scoped></style>