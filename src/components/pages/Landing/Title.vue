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
        font-size: 5.25vw;
        font-weight: 400;
        
    }

@media (max-width: 1000px) {
    #title {
        font-size: 8vw;
        justify-content: center;
    }
    

}


@media (max-width: 600px) {
        #title {
        font-size: 12vw;
        justify-content: center;
        }

        text {
            width: 90%;
            display: flex;

        }
    }
    

</style>