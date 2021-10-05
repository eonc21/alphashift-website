<template>
    <div>
        <text id='subtitle'>
            {{ subtitle }}
        </text>

        <!-- <vue-typer text='Hello World! I was registered locally!'></vue-typer> -->

    </div>
</template>

<script>
// ES6
// import {VueTyper} from 'vue-typer'


    export default {
        name: 'Subtitle',

        components: {
            // VueTyper,
        },

        props: {
            subtitle: String,
        }

        
    }
</script>

<style scoped>

    #subtitle {
        
        font-size: 1.9rem;
    }


</style>