<template>
  <div id='conclusion-page'>
      <div id='container'>
            <PageHeader text="INTERESTED? CONTACT US." />
      <div id='form-container'>
          <Contact />
      </div>
      </div>
      
      
  </div>
  <footer>
      <div id='container'>

    <div class='info'>
        <p>Follow us on...</p>
    </div>

    <div id='footer-text'>
        <div class='social'>
            <div class='image-container'>
                <img src="https://res.cloudinary.com/gromceri-test/image/upload/v1633903356/AlphaShift/linkedin-logo-white_juanmj.png" alt="">
            </div>
            <a href='#'>
            </a>
        </div>
        

        <div class='social'>
            <div class='image-container'>
                <img id='twitter' src="https://res.cloudinary.com/gromceri-test/image/upload/v1633903503/AlphaShift/twitter-icon-18-256_pw56yc.png" alt="">
            </div>
            <a href='#'>
            </a>
        </div>

        <div class='social'>
            <div class='image-container'>
                <img src="https://res.cloudinary.com/gromceri-test/image/upload/v1633903356/AlphaShift/linkedin-logo-white_juanmj.png" alt="">
            </div>
            <a href='#'>
            </a>
        </div>
        
        
    </div>
    <div class='info' id='info'>
        <p>2021 AlphaShift Consultancy Group, the Netherlands-based student-led consultancy organization.</p>
    </div>
      </div>
    </footer>
</template>

<script>
import Contact from '../Contact.vue'
import PageHeader from '../PageHeader.vue'

export default {

    name: 'Conclusion',

    components: {
        PageHeader,
        Contact,

    },

    props: {

    },


}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');


#conclusion-page {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background-color: #171717;
    color: rgba(255, 255, 255, 0.856);
}

#container {
    display: flex;
    height: 80%;
    justify-content: space-between;
    flex-direction: column;
    align-items: center;
    width: 100%;

}

#form-container {
    width: 60%;
    height: 550px;
    /* border: 1px solid pink; */
    justify-content: center;

}

footer {
    display: flex;
    flex-shrink: 0;
    background-color: black;
    width: 100%;
    height: 350px;
    justify-content: center;
    align-items: center;
    align-content: center;
}

#footer-text {
    display: flex;
    color: white;
    /* height: 40%; */
    width: 15%;
    justify-content: space-evenly;
    font-size: 1.75vw;
    align-items: center;
    height: 30%;
    text-align: center;
    margin:auto;

}

a { 
    text-decoration: none;
    color: rgba(255, 255, 255, 0.856);
    font-family: "Poppins", sans-serif;

}

.social {
    display: flex;
    /* width:  */
}

.image-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    align-content: center;
    justify-content: center;
    width: 55px;
    border-radius: 5px;
    height: 55px;
    /* margin-right: 20px; */
    background-color: rgba(119, 26, 26, 0.904);
}

img {
    width: 90%;
    height: 90%;
}

#twitter {
    width: 55%;
    height: 55%;
}

.info {
    display: flex;
    justify-content: center;
    text-align: center;
    align-self: center;
    align-content: center;
    width:30%;
    color: rgba(255, 255, 255, 0.849);
    height: 30%;
    font-size: 1.5vw;
    font-family: "Poppins", sans-serif;
}

#info {
    color: #868686;
    font-size: 1vw;
}

p {
    align-self: center;
}

#container {
    display: flex;
    flex-direction: column;
    align-self: center;
    /* flex:1; */
    justify-content: space-evenly;
    height: 80%;

}

</style>