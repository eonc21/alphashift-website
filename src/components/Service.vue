<template>
    <div id="service">
        <div id='icon-container'>
            <img :src="service.picture"/>
        </div>
        <h3>
            {{ service.text }}
        </h3>
        <p>
            {{ service.description }}
        </p>
        

    </div>
</template>

<script>
    export default {

        name: 'Service',

        props: {
            service: Object,
        }
        


        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

#service {
    display: flex;
    justify-content:center;
    width: 80%;
    align-self: center;
    text-align: center;
    margin: auto;
    flex-direction: column;
    /* margin: 15px; */
}

h3, p {
    
    font-family: 'Poppins', sans-serif;
}

h3 {
    font-size: 1.4vw;
    font-weight: 400;
    color: rgba(255, 255, 255, 0.85);
}

p {
    font-size: 1.1vw;
    color: #868686;
}

#icon-container {
    width: 4.5vw;
    height: 4.5vw;
    /* border: solid 1px pink; */
    align-self: center;
    margin: 0.8vw;
    margin-top: 0vw;
    /* background: red; */

}

img {
    width: 100%;
    height: 100%;
}

@media (max-width: 600px){
    #service {
        width: 90%;
        flex-direction: column;
    
    }

    h3 {
        font-size: 2rem;

    }

    p {
        font-size: 1.25rem;
        width: 90%;
        align-self: center;
        margin-bottom: 10vh;
    }

    #icon-container {
        width: 4rem;
        height: 4rem;
    }
    
}

</style>