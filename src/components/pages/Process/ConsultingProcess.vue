<template>
    <div class='process-page' id="page">
        <!-- <div class="title">
            <p>OUR CONSULTING PROCESS</p>
        </div> -->
        <div class ='process-page smaller'>
            <!-- <animated-component> -->
            <ProcessContainer :titles="titles.titlesbox1" :isLeft="true"/>

            <LineContainer />

            <ProcessContainer :titles="titles.titlesbox2"/>
            <!-- </animated-component> -->

        </div>
        
    </div>
</template>

<script>
import ProcessContainer from './ProcessContainer.vue'
import LineContainer from './LineContainer.vue'
let message1 = "STRATEGY CONSULTING & DELIVERABLES"
let message2 = "AI/ML MODELLING AND DATA ANALYTICS"

let width = window.innerWidth

if (width < 600) {
    message2 = "STRATEGY CONSULTING & DELIVERABLES";
    message1 = "AI/ML MODELLING AND DATA ANALYTICS"
}
    export default {
        name: 'ConsultingProcess',

        props: {

        },

        components: {
            ProcessContainer,
            LineContainer,

        },

        data() {
            return {
                titles: {
                    titlesbox1: ["UNDERSTANDING THE PROBLEM", message1],
                    titlesbox2: ["DATA MODELLING & ENGINEERING", message2]
                },
            
            }
        }

    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400&display=swap');

.process-page {
    font-family: "Oswald", sans-serif;

    display: flex;
    /* justify-content: center; */
    /* border: 1px solid slateblue; */
    width: 100%;
    height: 100%;
    
/* background-size: 100%; */
    /* background-image; */
    
}

#page {
    flex-direction: column;
    background-image: linear-gradient(0deg, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)),
     url('https://res.cloudinary.com/gromceri-test/image/upload/v1633734401/AlphaShift/samson-ZGjbiukp_-A-unsplash_ezrblm.jpg');
     /* mix-blend-mode: normal; */
    background-size: cover;
        filter: grayscale(50%);

    background-repeat: no-repeat;

}

.smaller {
    width: 65%;
    height: 75%;
    justify-content: space-between;
    align-self: center;
    letter-spacing: 2px;
    margin:auto;
    min-width: 900px;
    min-height: 550px;
}

.title {
    display: flex;
    width: 100%;
    height: 7.5%;
    align-self: flex-start;
    /* border: 1px yellow solid; */
    background: #661111;
    color: rgba(255, 255, 255, 0.85);
    justify-content: center;
    text-align: center;
}

p {
    font-size: 1.5rem;
    margin:auto;
}

/* #lines {
    display: flex;
    width: 400px;
} */

@media (max-width: 1000px) {
    .process-page {
        height: 100vh;
        justify-content: center;

    }

    .smaller {
        height: 65vh;
        width: 80vw;
        align-self: center;
        margin-right: 200px;
        margin-left: 200px;
        

    }

}

@media (max-width: 600px) {
    .process-page {
        display: flex;
        flex-direction: column;
        align-items: center;
        height: fit-content;

    }

    #page {
        background: #171717;
    }

   
    .smaller {
        width: 80%;
        margin: 15% 0%;
        justify-content: space-evenly;
        flex-direction: column;
        min-width:unset;
        min-height: unset;

    }
}

</style>