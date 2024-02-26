<template>
    <Chapter number="12" container-title="component v-model">
        <Block section-name="">
            <C12component v-model="count"/>
        </Block>
    </Chapter>
</template>

<script setup lang="ts">
import Chapter from './common/chapter.vue'
import Block from './common/block.vue'
import C12component from './innerComponent/C12component.vue'
import { ref } from 'vue'

const count = ref(0);
</script>

<style scoped>

</style>