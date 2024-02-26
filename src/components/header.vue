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
    box-sizing: border-box;
    position: fixed;
    top: 0;
    width: 100vw;
    padding: 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #eee;
    background-color: #fff;
}

section {
    display: flex;
    gap: 8px;
    align-items: end;
}
section:first-child {
    margin-right: 16px;
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