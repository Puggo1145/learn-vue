<template>
    <h1>Chapter {{ number }} - {{ props.containerTitle }}</h1>
    <MainContainer>
        <slot></slot>
    </MainContainer>
</template>

<script setup lang="ts">
import MainContainer from '../common/mainContainer.vue';

interface Props {
    number: string,
    containerTitle: string
}
const props = defineProps<Props>()
</script>

<style scoped></style>