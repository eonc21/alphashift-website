<template>
    <div id="btn" @click="menuClick">
        <img src="https://res.cloudinary.com/gromceri-test/image/upload/v1634483898/AlphaShift/unique_2_1_lwo5m3.png" >
    </div>
</template>

<script>
    export default {

        name: 'MenuButton',

        components: {

        },

        props: {

        },

        methods: {
            // menuClick: function() {
            //     alert("yoooooo")
            // }
        }
        
    }
</script>

<style scoped>

#btn {
    height: 75px;
    width: 75px;
    border: 0.5px rgba(255, 255, 255, 0.85) solid;
    font-size: 2.75rem;
    padding:10px 5px 5px 5px;
    color: rgba(255, 255, 255, 0.835);
    font-weight: 100;
}

@media (max-width: 600px) {

    #btn {
        height: 0px;
        width: 0px;
        visibility: hidden;
    }
    
}


</style>