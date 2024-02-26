<template>
    <h1>Chapter 6 - handle event</h1>
    <MainContainer>
        <Block section-name="receive event object">
            <p>{{ result }}</p>
            <input type="text" v-model="messageFromInput" placeholder="password" />
            <button @click="cipher(messageFromInput, $event)">submit</button>
        </Block>
        <Block section-name="keyboard listener">
            <p>New Value will be filled when enter</p>
            <p v-if="valueForKeyboard.showOnDOM">{{ valueForKeyboard.value }}</p>
            <input type="text" v-model="valueForKeyboard.value" @keyup.enter="valueForKeyboard.showOnDOM = true" />
        </Block>
    </MainContainer>
</template>

<script setup lang="ts">
import Block from './common/block.vue'
import MainContainer from './common/mainContainer.vue';
import { ref } from 'vue';

const messageFromInput = ref('');
const password = 'hello world'
const result = ref('Waiting'); // Empty by default

const valueForKeyboard = ref({
    value: '',
    showOnDOM: false
});

function cipher(message: string, event: Event) {
    if (message === password) {
        result.value = 'password correct';
    } else {
        result.value = `password from ${event.currentTarget} is not correct`;
    };
}
</script>

<style scoped>
input {
    margin-bottom: 16px;
}
</style>