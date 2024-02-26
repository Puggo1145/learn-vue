<script setup lang="ts">
interface Props {
    sectionName: string,
    other?: unknown
}
const { sectionName } = defineProps<Props>()
</script>

<template>
    <section>
        <h4>{{ sectionName }}</h4>
        <slot />
    </section>
</template>


<style scoped>
section {
  min-width: 140px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 16px;
  border-radius: 8px;
  background-color: #eee;
}

section:nth-child(3n),
section:last-child {
  flex: 1;
}
</style>