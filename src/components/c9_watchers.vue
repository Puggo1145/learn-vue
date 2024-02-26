<template>
    <Chapter number="9" container-title="Watchers">
        <Block section-name="watch a state">
            <p>state change time : {{ stateChangeTime }}</p>
            <input type="text" v-model="inputValue" />
        </Block>
        <Block section-name="watch a property in an object">
            <p>This requires a getter function</p>
            <p>state change count : {{ stateChangeCount }}</p>
            <button @click="object.num++">count: {{ stateChangeCount }}</button>
        </Block>
        <Block section-name="immediate watch when mounted">
            <p>{{ count }}</p>
            <p>state change count: {{ immediateWatchChangeCount }}</p>
            <button @click="count++">add count</button>
        </Block>
        <Block section-name="watch effect">
            <p>{{ isFetching ? 'fetching...' : `${todoId}-${data}` }}</p>
            <button @click="todoId++">increase id</button>
        </Block>
    </Chapter>
</template>

<script setup lang="ts">
import Chapter from './common/chapter.vue';
import Block from './common/block.vue'
import { ref, watch, watchEffect } from 'vue';

const inputValue = ref('');
const stateChangeTime = ref(0);
watch(inputValue, () => stateChangeTime.value++)

const object = ref({ num: 0 })
const stateChangeCount = ref(0)
watch(
    () => object.value.num,
    () => stateChangeCount.value++
)

const count = ref(0);
const immediateWatchChangeCount = ref(0);
watch(
    count,
    () => {
        immediateWatchChangeCount.value++
    },
    { immediate: true }
)

type Response = { title: string };
const todoId = ref(1)
const data = ref<string | Response>('')
let isFetching = ref(false); // false by default
watchEffect(async () => {
    isFetching.value = true;
    const response = await (await fetch(`https://jsonplaceholder.typicode.com/todos/${todoId.value}`)).json() as Response
    data.value = response.title;
    isFetching.value = false;
});
// watch Effect immediatedly runs at the first time a component has been mounted.
// It also tracks dependents change automatically when refered in a function. 
</script>

<style scoped></style>