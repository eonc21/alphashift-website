<template>
    <div id="what-are-we-page">
        <div class="half-page red">
            <div id="image-container">
                <!-- <img src="../../assets/logo.png" /> -->
            </div>
        </div>
        <div class="half-page black"></div>

    </div>
</template>

<script>
    export default {
        name: 'WhatWeDo',

        components: {

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
    width: 80%;
    height: 80%;
    background-image: linear-gradient(0deg, rgba(22, 22, 22, 0.85), rgba(22, 22, 22, 0.85)), url('../../assets/whatwedo.jpg');
    background: url('../../assets/whatwedo.jpg');
    mix-blend-mode: normal;
    background-size: cover;
}

.black {
    background: #171717;
}

.red {
    background: #851d1de1;
}

</style>