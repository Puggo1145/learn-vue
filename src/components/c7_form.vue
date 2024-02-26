<template>
    <h1>Chapter 7 - Form</h1>
    <MainContainer>
        <Block section-name="bind DOM value using v-model"> 
            <p>Text below is the input value</p>
            <p>{{ inputValue }} - {{ textareaValue }}</p>
            <input type="text" v-model.lazy="inputValue" />
            <textarea cols="30" rows="10" v-model="textareaValue"></textarea>
        </Block>
        <Block section-name="checkBox v-model bind">
            <label for="checkBox">IsChecked?: {{ checkedBoxValue }}</label>
            <input id="checkBox" type="checkbox" v-model="checkedBoxValue"/>
        </Block>
        <Block section-name="multi checkbox bind">
            <p>Checked Names:</p>
            <p>{{ multicheckBoxBind.join(', ') }}</p>
            <ul>
                <li v-for="name in names">
                    <label :for="name">{{ name }}</label>
                    <input type="checkbox" :id="name" :value="name" v-model="multicheckBoxBind" />
                </li>
            </ul>
        </Block>
        <Block section-name="Checker">
            <p>Picked: {{ pickValue }}</p>
            <ul>
                <li v-for="name in names">
                    <label :for="name">{{ name }}</label>
                    <input type="radio" :id="name" :value="name" v-model="pickValue" />
                </li>
            </ul>
        </Block>
        <Block section-name="select and options">
            <p>select: {{ selectValue }}</p>
            <select v-model="selectValue">
                <option disabled value="">Please Select One</option>
                <option v-for="name in names" :value="name">{{ name }}</option>
            </select>
        </Block>
        <Block section-name="model decorator: v-model.number.trim">
            <p>{{ numberInputValue ? numberInputValue : 'waiting for input...' }}</p>
            <p>Type: {{ typeof numberInputValue }}</p>
            <input type="text" v-model.number.trim="numberInputValue">
        </Block>
    </MainContainer>
</template>

<script setup lang="ts">
import Block from './common/block.vue'
import MainContainer from './common/mainContainer.vue';
import { ref } from 'vue';

const inputValue = ref(''); // Empty by default
const textareaValue = ref('');

const checkedBoxValue = ref(false); // false by default

const multicheckBoxBind = ref([]);
const names = ref(['Jack', 'Henry', 'Andrew']);

const pickValue = ref('');

const selectValue = ref('');

const numberInputValue = ref<number | string>('');
</script>

<style scoped>
input {
    margin-bottom: 16px;
}

</style>