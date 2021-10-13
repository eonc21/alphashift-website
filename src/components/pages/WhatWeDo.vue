<template>
    <div id="what-are-we-page">
        <div class="half-page red">
            <div id="image-container">
                <img src="../../assets/whatwedo.png" />
            </div>
            
        </div>
        <div class="half-page black">
            <div id="text-container">
                <animated-component>
                    <PageHeader text="WHAT WE DO" />
                </animated-component>

                <div id="slides-container">
                        <VueperSlides  class="no-shadow" :arrows="false" :bullets="true" fixed-height="100%">
                        <vueper-slide v-for="(slide, i) in slides" 
                            :content="slide.content" 
                            :key="i"
                            :style="`display: flex; 
                            color: rgba(255, 255, 255, 0.82); 
                            font-size: 1.45vw;
                    `"/>
                    </VueperSlides>
                    
                </div>

                
                
            </div>
          
            <div id='button-container'>
                <Button link="#conclusion-page" text="WORK WITH US" />

            </div>

            

            

        </div>

    </div>
</template>

<script>
import PageHeader from '../PageHeader.vue'
import AnimatedComponent from '../AnimatedComponent.vue'
import Button from '../Button.vue'
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

let font = 1.45
let w = 30

let width = window.innerWidth
if (width < 600) {
    font = 4.5
    w = 80
}


    export default {
        name: 'WhatWeDo',

        components: {
            PageHeader,
            VueperSlides, 
            VueperSlide,
            AnimatedComponent,
            Button

        },
        data: () => ({
            slides: [
                    {
                    title: 'Slide #1',
                    content: `<div style="display: flex; justify-content: center; margin-bottom: 40px;
                            text-align: center; width: ${w}vw; font-size: ${font}vw; align-self:">
                            As a data consultancy organization, we excel at 
                            supporting and leading our clients through a variety 
                            of data-related business solutions tailored to 
                            their respective industries. AlphaShift provides 
                            bespoke data services solutions for large and small 
                            private organizations.</div>`
                    },

                    {
                    title: 'Slide #2',
                    content: `<div style="display: flex; justify-content: center; 
                            text-align: center; width: ${w}vw; font-size: ${font}vw; align-self:">The services include exploratory data analysis, data
                                management, creating prediction models, and 
                                the production of entire decision support systems and
                                data-powered products.`
                    },

                    {
                    title: 'Slide #3',
                    content: `<div style="display: flex; justify-content: center; 
                            text-align: center; width: ${w}vw; font-size: ${font}vw; align-self:">We perform extensive study and analysis to discover 
                            the correct technology to  power it all, keeping our 
                            clients' business demands at the forefront of our approach.`
                    },

                    
                ]
            }),

        props: {

        }
        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

#what-are-we-page {
    display: flex;
    width: 100%;
    height: 100%;
    
}

.half-page {
    width: 50%;
    color: rgba(255, 255, 255, 0.80);
    display: flex;
    justify-content: right;

}

#image-container {
    display: flex;
    justify-content: right;
    width: 88%;
    height: 88%;
    /* background: linear-gradient(0deg, rgba(22, 22, 22, 0.90), rgba(22, 22, 22, 0.50)); */
    border-radius: 25px;
    z-index: 2;
    mix-blend-mode: normal;
    background-size: cover;
}

#slides-container {
    width: 90%;
    height: 60%;

}

/* .vueperslides_bullets {
    position: inherit;
    padding: 100px;
} */

img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 0px 0 0px 20px;
    z-index: 1;
}

.black {
    background: #171717;
    display: flex;
    justify-content: space-evenly;
    flex-direction: column;
}

#text-container {
    width: 95%;
    height: 75%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    align-self: center;
    font-family: 'Poppins', sans-serif;
}

#button-container {
    margin-bottom: 7vh;
    display: flex;
    justify-content: center;
    align-items: center;

}

span {
    font-size: 1.9rem;
}


.red {
    background: #5a0d0d;
}

@media (max-width: 600px) {

    #what-are-we-page {
        height: fit-content;
        flex-direction: column;
    }

    .half-page {
        width: 100%;
    }

    .red {
        order: 2;
        justify-content: center;
        height:65vh;

    }

    .black {
        order: 1;
        height:100vh;

       /* height: fit-content; */
    }

    #image-container {
        justify-content: center;
        border-radius: 0;
        width: 100%;
        height: 100%;
    }

    img {
        border-radius: 0;
    }

}



</style>