<template>
    <Chapter number="11" container-title="basic of component">
        <Block section-name="pass props to component + event listener">
            <div class="book-wrapper" :style="{fontSize: postFontSize + 'em'}" >
                <C11component 
                    v-for="book in bookList" 
                    :key="book.id" 
                    :book="book" 
                    @enlarge-text="postFontSize += 0.1"
                />
            </div>
        </Block>
    </Chapter>
</template>

<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
import C11component from './innerComponent/C11component.vue';
import { ref } from 'vue';

export interface BookType {
    id: number
    title: string
    content: string
}
const bookList = ref<BookType[]>([
    {
        id: 1,
        title: 'Journey To the West',
        content: 'cadcadcakcjblksjcnqlK3fj,qwc'
    },
    {
        id: 2,
        title: 'The second book',
        content: 'cadcadcakcjblksjcnqlK3fj,qwc'
    },
])

const postFontSize = ref(1);
</script>

<style scoped>
.book-wrapper {
    display: flex;
    justify-content: space-evenly;
}
</style>