<script lang="ts" setup>
import { ref, shallowRef } from 'vue';

const deepTrackObject = ref({
    number: 0
});
const shallowTrackOfRef = shallowRef({
    number: 0
});
</script>

<template>
    <h1>Chapter2 - reactivity</h1>
    <div class="main-container">
        <section class="deepTrackOfRef">
            <h4>deep track of Ref</h4>
            <p>number in an object: {{ deepTrackObject.number }}</p>
            <button @click="deepTrackObject.number++">increase number</button>
        </section>
        <section class="deepTrackOfRef">
            <h4>shallow Ref</h4>
            <span>the change of number won't trigger update</span>
            <span>but the value will update and represented in next update</span>
            <p>number in an object: {{ shallowTrackOfRef.number }}</p>
            <button @click="shallowTrackOfRef.number++">increase number</button>
        </section>
    </div>
</template>

<style scoped>

</style>