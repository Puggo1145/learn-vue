<script setup lang="ts">
</script>

<template>
    <div class="main-container">
        <slot />
    </div>
</template>


<style scoped>
.main-container {
  width: 864px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}
</style>