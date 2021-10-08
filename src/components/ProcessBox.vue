<template>
    <div id='box-container'>
        <h4>
            {{ title }}
        </h4>

        <text>
            {{ content }}
        </text>

    </div>
</template>

<script>
    export default {
        name: 'ProcessBox',

        props: {
            title: String,
            content: String,
        }
        
    }
</script>

<style scoped>

#box-container {
    width: 100%;
    height: 200px;
    border: 1px solid white;
    color: white;
}

</style>