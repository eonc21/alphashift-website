<template>
    <div id='main-container'>
        <ProcessBox />
        <div id='line'></div>
        <ProcessBox />


    </div>
</template>

<script>
import ProcessBox from '../components/ProcessBox.vue'
    export default {
        name: 'ProcessContainer',
        props: {
            // text: String,
            // content: String,
        },

        components: {
            ProcessBox,
        }
        
    }
</script>

<style scoped>

#main-container {
    display: flex;
    /* border: 1px solid orange; */
    flex-direction: column;
    justify-content: space-between;
    align-self: center;
    width: 25%;
    height: 100%;
    color: white;
}

#line {
    border-left: 1px solid white;
    align-self: center;
    height: 35%;
}
</style>