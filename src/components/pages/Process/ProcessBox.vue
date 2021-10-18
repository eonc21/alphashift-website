<template>
    <div id='box-container'>
        <p>
            {{ title }}
        </p>

        <!-- <text v-if="hasContent">
            Is a data solution suitable?
        </text> -->

    </div>
</template>

<script>
    export default {
        name: 'ProcessBox',

        props: {
            title: String,
            content: String,
            hasContent: Boolean,
        }
        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

#box-container {
    display: flex;
    justify-content: space-evenly;
    flex-direction: column;
    width: 100%;
    font-size: 1.55vw;
    font-weight: 300;
    height: 27.5%;
    /* background: #000000a6; */
    backdrop-filter: blur(8px);

    border: 1px solid rgba(255, 255, 255, 0.85);
    color: rgba(255, 255, 255, 0.856);
    min-width: 200px;

}
 
p {
    width: 80%;
    /* height: 40%; */
    align-self: center;
    min-width: 160px;

}

text {
    width: 80%;
    align-self: center;
    font-size: 0.9vw;
    height: 30%;
    font-family: "Poppins", sans-serif;
    margin-bottom: 10%;
    color: #868686;
    min-width: 160px;

}

@media (max-width: 1000px) {

    #box-container {
        height: 170px;
        font-size: 2.65vw;
    }

    text {
        width: 90%;
        letter-spacing: 1px;
        font-size: 1.75vw;
    }
    
}

@media (max-width: 600px) {

    #box-container {
        height: 190px;
        justify-content: center;
        width:80vw;
        border: 0.5px solid rgba(255, 255, 255, 0.856);
        font-size: 7vw;
    }
    text {
        width: 90%;
        letter-spacing: 1px;
        font-size: 4.5vw;
    }
    
}

</style>