<template>
    <div class='process-page'>
        <div class ='process-page smaller'>
        <ProcessContainer />
        <LineContainer />
        <ProcessContainer />
            
        </div>
    </div>
</template>

<script>
import ProcessContainer from '../ProcessContainer.vue'
    export default {
        name: 'ConsultingProcess',

        props: {

        },

        components: {
            ProcessContainer,

        },

    }
</script>

<style scoped>

.process-page {
    display: flex;
    justify-content: center;
    /* border: 1px solid slateblue; */
    width: 100%;
    height: 100%;
    background: #171717;
}

.smaller {
    width: 70%;
    height: 70%;
    justify-content: space-between;
    align-self: center;
}

</style>