<script setup lang="ts">

</script>

<template>
    <header>
        <section class="header-left">
            <img src="../assets/vue.svg" alt="">
            <section>
                <h2>A Vue Feature Gallery</h2>
                <p>based on documentation</p>
            </section>
        </section>
        <section class="header-right">
            <a href="https://cn.vuejs.org/guide/quick-start.html" target="_blank">
                <button>documentation</button>
            </a>
        </section>
    </header>
</template>

<style scoped>
header {
    padding: 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    border-bottom: 1px solid #eee;
}

section {
    display: flex;
    gap: 8px;
    align-items: end;
}

h2,
p {
    margin: 0;
}

p {
    font-size: 12px;
    margin-bottom: 5px;
}
</style>