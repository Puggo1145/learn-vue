<template>
    <div>
        {{ message }}
    </div>
</template>

<script setup lang="ts">
type Props = {
    message: string
}
const { message } = defineProps<Props>();
</script>

<style scoped>
div {
    box-sizing: border-box;
    padding: 8px;
    background-color: #fff;
    margin-bottom: 8px;
    border-radius: 8px;
}
</style>