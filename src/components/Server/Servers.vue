<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <div>
                <appServer v-for="server in servers" :server=s erver></appServer>
            </div>
        </ul>
    </div>
</template>

<script>
import Server from './Server.vue';

export default {
    data: function () {
        return {
            servers: [
                { id: 1, status: 'normal' },
                { id: 2, status: 'critical' },
                { id: 3, status: 'unknow' },
                { id: 4, status: 'overload' },
                { id: 5, status: 'underload' }
            ]
        }
    },

    components: {
        appServer: Server
    }
}
</script>

<style>

</style>
