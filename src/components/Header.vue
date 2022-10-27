<template>
    <header @click="$emit('toggleDarkMode')">
        <p>{{darkmode == "dark" ? "Light Mode" : "Dark Mode"}}</p>
    </header>
</template>

<script>

export default {
    name: 'HeaderElem',
    props: ['darkmode']
}

</script>

<style scoped>

header {
    margin-top: -50px;
    padding-left: 15px;
    padding-right: 15px;
    color: var(--text-color);
    background-color: var(--elements-color);
    margin-bottom: 10px;
    border-radius: 10px;
}

</style>