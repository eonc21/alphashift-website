<template>
    <div id='text-container'>
        <p>We are students from different backgrounds, who believe they can create a beneficial impact on your company by <span>delivering cutting edge data & AI solutions</span>. We believe that consulting should not be only limited to management and strategy, but it should also be supported by data. Organizations can use AI to detect trends and draw insights from it
in order to make better decisions.

<br/> <br/>Therefore,  we have started the first ever student based AI & Data Consultancy organization, AlphaShift Consulting Group.</p>
         

    </div>
</template>

<script>
    export default {
        name: 'WeAre',

        props: {
            text: String,
        }
        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');


#text-container {
    display: inline-block;
    width: 80%;
    font-family: 'Poppins', sans-serif;
    color: rgba(255, 255, 255, 0.80);
    margin:auto;
}

p {
    width: 90%;
    font-size: 1.7vw;
    
    align-self: center;
}

span {
    color: #ff4747e3;

}

</style>