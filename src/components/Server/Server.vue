<template>
    <li class="list-group-item" @click="selectServer()">
        Server #{{ server.id }}
    </li>
</template>

<script>
    import { serverBus } from '../../main.js';
    export default {
        props: ['server'],
        methods: {
            selectServer() {
                serverBus.$emit('activeServer', this.server);
            }
        }
    }
</script>
