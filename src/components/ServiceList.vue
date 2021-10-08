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
    align-items: center;
    align-content: center;
    align-self: center;
    justify-content:center;
    margin:auto;
    margin-top: 0px;
}


#service {
    display: flex;
    justify-content: center;
}

@media (max-width: 1000px){
    #service-list {
        flex-direction: column;
        width: 100%
    
    }
    
}

</style>