<template>
    <div id="who-we-are-page">
        <div id="text-container">
            <PageHeader text="WHO ARE WE?" />
            <WeAre />
        </div>

    </div>
</template>

<script>
import PageHeader from "../PageHeader.vue"
import WeAre from "../WeAre.vue"
    export default {

        name: 'WhoAreWe',

        components: {
            PageHeader,
            WeAre,
        },

        props: {

        },
        
    }
</script>

<style scoped>

#who-we-are-page {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background-image: linear-gradient(0deg, rgba(22, 22, 22, 0.85), rgba(22, 22, 22, 0.85)), url('../../assets/landing.jpg');
    mix-blend-mode: normal;
    background-size: cover;
}

#text-container {
    width: 85%;
    height: 85%;
    display: flex;
    align-self: center;
    justify-content: center;
    flex-direction: column;
}

</style>