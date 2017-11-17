<template>
    <li class="listitem">{{content}}</li>
</template>

<script>

    export default {
        name: "list-item",
        props: ["content"]
    }

</script>

<style scoped>
    .listitem {
        display: block;
        text-align: center;
    }
</style>