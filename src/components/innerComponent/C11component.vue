<template>
    <div>
        <p>Book - {{ book.id }}</p>
        <h4>{{ book.title }}</h4>
        <p>{{ book.content }}</p>
        <button @click="emitEvent">enlarge text</button>
    </div>
</template>

<script setup lang="ts">
import { BookType } from '../c11_basicOfComponent.vue';

const emit = defineEmits<{(e: 'enlarge-text'): void}>()
const { book } = defineProps<{ book: BookType }>()

function emitEvent() {
    emit('enlarge-text')
}
</script>

<style scoped>
div {
    display: flex;
    flex-direction: column;
    align-items: start;
}
</style>