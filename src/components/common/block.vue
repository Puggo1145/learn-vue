<script setup lang="ts">
const { sectionName } = defineProps({
    sectionName: String
})
</script>

<template>
    <section>
        <h4>{{ sectionName }}</h4>
        <slot />
    </section>
</template>


<style scoped></style>