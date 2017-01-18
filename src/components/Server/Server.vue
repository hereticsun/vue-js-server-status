<template>
    <li class="list-group-item">
        Server #{{ server.id }}: {{ server.status }}
    </li>
</template>

<script>
    export default {
        props: {
            server: Object
        },

    }
</script>

<style>

</style>
