<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">please select a server</p>
        <p v-else>Server #{{ server.id }} is {{ server.status }}</p>
        <button @click="resetStatus">Change To Normal</button>
    </div>
</template>

<script>
import { serverBus } from '../../main.js';
export default {
    data: function () {
        return {
            server: null
        }
    },
    methods: {
        resetStatus: function(){
            this.server.status = 'normal';
        }
    },
    created() {
        serverBus.$on('serverSelected', (server) => {
            this.server = server;
        });
    }
}
</script>
   
<style>

</style>
