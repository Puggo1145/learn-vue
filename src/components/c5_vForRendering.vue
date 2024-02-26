<template>
    <h4>Chapter 5 - v-for rendering</h4>
    <MainContainer>
        <Block>
            <h4>v-for rendering</h4>
            <p>The scope of v-for is similar to JS</p>
            <ul>
                <li v-for="(item, index) in list">{{ index + 1 }}: {{ item.message }}</li>
            </ul>
        </Block>
        <Block>
            <h4>direct deconstruction of v-for</h4>
            <ul>
                <li v-for="({ message }) in list">{{ message }}</li>
            </ul>
        </Block>
        <Block>
            <h4>v-for of Object</h4>
            <ul>
                <li v-for="(value, key, index) in object">
                    {{ index }} - {{ key }}: {{ value }}
                </li>
            </ul>
        </Block>
        <Block section-name="Python Style For in ">
            <p>Number starts from 1</p>
            <ul>
                <li v-for="item in 3">{{ item }}</li>
            </ul>
        </Block>
        <Block section-name="best practice of v-for + v-if">
            <ul>
                <li v-for="{ message } in list">
                    <p v-if="message === 'foo'">{{ message }}</p>
                </li>
            </ul>
        </Block>
        <Block section-name="state manager (key)">
            <p>This is similar to React</p>
            <p>Every element will be tracked separately based on id</p>
            <ul>
                <li v-for="{ id, message } in list" :key="id">{{ message }}</li>
            </ul>
        </Block>
        <Block section-name="v-for on component">
            <p>Component can be iterated</p>
            <p>However, data can only be received via props</p>
            <ul>
                <C5component v-for="{ id, message } in list" :key="id" :message="message"/>
            </ul>
        </Block>
        <Block section-name="filter array with computed property 1">
            <p>Use computed property when we don't want to alter original array</p>
            <ul>
                <li v-for="number in evenNumbers">{{ number }}</li>
            </ul>
        </Block>
        <Block section-name="filter array when computed property is not valid">
            <p>Use function to achieve the same result</p>
            <ul v-for="numberArray in numberSets">
                <li v-for="number in evenNumbersFn(numberArray)">{{ number }}</li>
            </ul>
        </Block>
    </MainContainer>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue';
import Block from './common/block.vue'
import MainContainer from './common/mainContainer.vue';
import C5component from './innerComponent/C5component.vue';

const list = ref([
    { id: 1, message: 'foo' },
    { id: 2, message: 'bar' },
    { id: 3, message: 'baz' },
])

const object = ref({
    title: 'Journey To the West',
    author: 'ChenEn Wu',
    sale: 90
})

const numbers = ref([1, 2, 3, 4, 5])
const evenNumbers = computed(() => numbers.value.filter(item => item % 2 === 0)); // a filtered array

// when computed property is not valid, especially in a nested array. Use function to achieve the same result
const numberSets = ref([
    [1, 2, 3, 4, 5],
    [6, 7, 8, 9, 10]
])
function evenNumbersFn(numbersArray: number[]) {
    return numbersArray.filter(item => item % 2 === 0);
}
</script>

<style scoped></style>