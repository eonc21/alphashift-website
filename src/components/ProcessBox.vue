<template>
    <div id='box-container'>
        <p>
            {{ title }}
        </p>

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
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    width: 100%;
    font-size: 1.75rem;
    font-weight: 300;
    height: 200px;
    /* background: #000000a6; */
    backdrop-filter: blur(8px);

    border: 1px solid rgba(255, 255, 255, 0.856);
    color: rgba(255, 255, 255, 0.856);
}
 
p {
    width: 80%;
    margin: auto;
    align-self: center;
}

</style>