<template>
    <div>
        <p>Child: {{ isShown ? 'This is shown' : '' }}</p>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isShown = ref(true); // show by default
const switchInvisibility = () => isShown.value = !isShown.value;

defineExpose({
    switchInvisibility
})
</script>

<style scoped></style>