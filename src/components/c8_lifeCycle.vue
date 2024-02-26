<template>
    <Chapter number="8" container-title="Component Life Cycle">
        <Block section-name="onMounted">
            <p>isComponentMounted: {{ isMounted }}</p>
        </Block>
        <Block section-name="onUpdate">
            <p>count: {{ count }}</p>
            <button @click="count++">Update</button>
        </Block>
    </Chapter>
</template>

<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
import { ref, onMounted, onUpdated } from 'vue'

const isMounted = ref(false); // false by default. true when mounted
const count = ref(0);

onMounted(() => isMounted.value = !isMounted.value);
onUpdated(() => { 
    console.log(document.getElementById('count')!.textContent);
});
</script>

<style scoped></style>