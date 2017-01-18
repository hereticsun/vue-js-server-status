<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Server Details are currently not updated</p>
        <div v-else>
            <p>Server #{{ server.id }} selected, Status: {{ server.status }}</p>
            <button @click="resetServer">Reset Server</button>
        </div>
    </div>

</template>

<script>
    import { serverBus } from '../../main.js';

    export default {
        data: function() {
            return {
                server: null
            }
        },
        methods: {
            resetServer() {
                this.server.status = 'Normal';
            }
        },
        created() {
            serverBus.$on('activeServer', (server) => {
                this.server = server;
            });
        }
    }
</script>
