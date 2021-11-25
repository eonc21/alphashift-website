<template>
<animated-component>
  <div id="member">
    <div id="member-image-container">
      <img id="img" :src="member.image" alt="picture of team member">
    </div>
    <h5 id="h5">
      {{ member.name }}
    </h5>
    <p id="p">
    {{ member.position }}

    </p>
    <a id="a" target="_blank" :href="member.linkedIn">
      <img id="linkedin" src="https://res.cloudinary.com/dbdtfa9qb/image/upload/v1637752901/alphashift/333-3339255_social-icon-linkedin-circle-logo-white_psbzcx.png" alt="linkedIn page">
    </a>
    </div>
</animated-component>

</template>

<script>
import AnimatedComponent from '../../AnimatedComponent.vue'
export default {
    name: "Member",

    props: {
        member: Object,
    },

    components: {
      AnimatedComponent,
    }



}
</script>

<style>

  #member {
    width: 100%;
    height: 67.5vh;
    margin: 65px 15px 65px 15px;
    display: flex;
    flex-direction: column;
    font-family: "Poppins", sans-serif;
    /* border: white solid 1px; */
  }

  #member-image-container {
    border: 1px solid white;
   width: 22vw;
   margin-bottom: 40px;
    height: 45vh;
    display: flex;
    justify-content: center;
    align-self: center;
    object-fit: cover;
  }

  #linkedin {
    margin: 10px;
    width: 30px;
    height: 30px;
  }

  #img {
    /* margin: 5px; */
     width:90%;
    height: 90%;
    border-radius: 0px;
  }

  #p {
    margin:10px;
    font-size: 1.5rem;
    font-weight: 300;
  }

  #h5 {
    margin:10px;
    font-size: 2.25rem;
    font-weight: 400;
    letter-spacing: 0.5px;
  }

</style>