<template>
    <div id='title'>
        <text>{{ title }}</text>
    </div>
</template>

<script>
    export default {
        name: 'Title',
        props: {
            title: String,
        }
        
    }
</script>

<style scoped>

    #title {
        display: flex;
        width: 100%;
        justify-content: space-between;
        font-size: 6.25rem;
        font-weight: 400;
        
    }

</style>