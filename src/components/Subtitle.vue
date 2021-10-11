<template>
    <div class='subtitle-container'>
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


    @media (max-width: 600px){

        #subtitle {
            font-size: 5vw;
            align-self: center;
            
        }

        .subtitle-container {
            display: flex;
            height: 30%;
            width: 100%;
        

        }
    } 


</style>