<template>
    <div>
        <p>{{ infoText }}</p>

    </div>
</template>

<script>
    export default {

        name: 'InfoSlide',

        props: {
            infoText: String,
        }
        
    }
</script>

<style scoped>

</style>