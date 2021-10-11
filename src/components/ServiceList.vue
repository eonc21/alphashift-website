<template>
    <div id='service-list'>
        <div :key="service.id" v-for="service in services" id='service'>
            <animated-component>
                <Service :service="service"/>

            </animated-component>

        </div>
    </div>
    
</template>

<script>
import Service from '../components/Service.vue'
import AnimatedComponent from './AnimatedComponent.vue'

    export default {
        name: 'ServiceList',

        props: {
            services: Array
        },

        components: {
            Service,
            AnimatedComponent,
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
    /* margin:auto; */
    margin-top: 0px;
}


#service {
    display: flex;
    justify-content: center;
}

@media (max-width: 600px){
    #service-list {
        flex-direction: column;
        width: 100%
    
    }
    
}

</style>