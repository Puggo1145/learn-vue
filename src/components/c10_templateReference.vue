<template>
    <Chapter number="10" container-title="template reference">
        <Block section-name="ref basic usage"> 
            <p>This input will be focused initially</p>
            <input type="text" ref="inputElement" />
        </Block>
        <Block section-name="ref on v-for">
            <ul>
                <li v-for="number in list" ref="listElement">{{ number }}</li>
            </ul>
        </Block>
        <Block section-name="ref on callback">
            <div :ref="(el) => el && console.log(el)">The ref of the div will be collected to its ref callback</div>
        </Block>
        <Block section-name="ref on component">
            <p>ref on component is the instance of the component</p>
            <Block section-name="" :ref="el => console.log(el)" />
        </Block>
        <Block section-name="use methods on child via component reference">
            <p>Use function exposed on child via ref</p>
            <C10component ref="child"/>
            <button @click="child?.switchInvisibility()">switch invisibility of child</button>
        </Block>
    </Chapter>
</template>

<script setup lang="ts">
import Chapter from './common/chapter.vue';
import Block from './common/block.vue'
import C10component from './innerComponent/C10component.vue';
import { ref, onMounted } from 'vue';

const inputElement = ref<null | HTMLInputElement>(null)
const listElement = ref<null | HTMLLIElement[]>(null);

const list = ref([1, 2, 3, 4, 5])

// If you want to get completion of methods exposed by other components, use InstanceType to instance the type of your component
type Child = InstanceType<typeof C10component> | null
const child = ref<Child>(null);

onMounted(() => {
    inputElement.value?.focus(),
    console.log(listElement.value);
    console.log(child);
})
</script>

<style scoped>

</style>