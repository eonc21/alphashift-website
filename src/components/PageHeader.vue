<template>
    <div id='header'>
        <text>{{ text }}</text>
        
    </div>
</template>

<script>
    export default {
        name: "PageHeader",

        props: {
            text: String,
            styling: String,
        }
        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400&display=swap');

#header {
    width:fit-content;
    height: fit-content;
    padding: 25px 55px 25px 55px;
    font-size: 2.75vw;
    letter-spacing: 2px;
    font-weight: 200;
    color: rgba(255, 255, 255, 0.85);
    font-family: 'Oswald', sans-serif;
    border: rgba(255, 255, 255, 0.85) solid 1px;
}

@media (max-width: 600px) {
    #header {
        display: flex;
        justify-content: center;
        margin: auto;
        padding: 10px 20px 10px 20px;
        align-self: center;
        font-size: 9vw;
    }

}

</style>