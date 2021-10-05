<template>
    <div id="landing-page">
        <div id='menu-container'>
            <MenuButton />
        </div>
        
        <div id='title-container'>
            <Title title="AlphaShift Consulting Group" />
            <Subtitle subtitle="the Netherlands' first student-based
                         data & AI services organization. " />
        </div>

    </div>
</template>

<script>
import Title from "../Title.vue"
import Subtitle from "../Subtitle.vue"
import MenuButton from "../MenuButton.vue"

    export default {
        name: 'Landing',

        components: {
            Title,
            Subtitle,
            MenuButton,
        },
        
        props: {

        }
    }

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

#landing-page {
    display: flex;
    justify-content: flex-start;
    width: 100%;
    flex-direction: column;
    height: 100%;
    background-color: #171717;
    color: rgba(255, 255, 255, 0.856);
}

#menu-container {
    height: 35%;
    display: flex;
    justify-content: left;
    margin: 50px 0px 0px 50px;

}

#title-container {
    height: 45%;
    justify-content: space-between;
    width: 70%;
    display: flex;
    text-align: left;
    margin-left: 7.5%;
    flex-direction: column;
    font-family: 'Poppins', sans-serif;

}



</style>