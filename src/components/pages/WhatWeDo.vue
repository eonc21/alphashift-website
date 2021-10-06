<template>
    <div id="what-are-we-page">
        <div class="half-page red">
            <div id="image-container">
                <img src="../../assets/whatwedo.jpg" />
            </div>
        </div>
        <div class="half-page black">
            <div id="text-container">
                <PageHeader text="WHAT WE DO" />
            </div>

        </div>

    </div>
</template>

<script>
import PageHeader from '../PageHeader.vue'

    export default {
        name: 'WhatWeDo',

        components: {
            PageHeader,

        },

        props: {

        }
        
    }
</script>

<style scoped>

#what-are-we-page {
    display: flex;
    width: 100%;
    height: 100%;
    
}

.half-page {
    width: 50%;
    color: rgba(255, 255, 255, 0.85);
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
    justify-content: center;
    flex-direction: column;
}

#text-container {
    width: 80%;
    height: 80%;
    display: flex;
    justify-content: center;
    align-self: center;
}

.red {
    background: #741414;
}

</style>