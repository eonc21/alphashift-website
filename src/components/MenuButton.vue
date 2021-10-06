<template>
    <div id="btn" @click="menuClick">
        ≡
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
            menuClick: function() {
                alert("yoooooo")
            }
        }
        
    }
</script>

<style scoped>

#btn {
    height: 50px;
    width: 50px;
    border: 1px rgba(255, 255, 255, 0.883) solid;
    font-size: 2.75rem;
    color: rgba(255, 255, 255, 0.835);
    font-weight: 100;
}

</style>