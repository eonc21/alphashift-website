<template>
    <div id='service-list'>
        <div :key="service.id" v-for="service in services" id='service'>
            <Service :service="service"/>

        </div>
    </div>
    
</template>

<script>
import Service from '../components/Service.vue'
    export default {
        name: 'ServiceList',

        props: {
            services: Array
        },

        components: {
            Service,
        }
        
    }
</script>

<style scoped>

#service-list {
    width: 90%;
    display: flex;
    align-self: center;
    justify-content: space-between;
    margin-top: 35px;
}

#service {
    display: flex;
    justify-content: center;
}

</style>