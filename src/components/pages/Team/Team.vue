<template>
  <div id="team-page" class="container">
      <div id="header-container">
        <animated-component>
            <PageHeader text="OUR TEAM"/>
        </animated-component>
      </div>
      
    <div id="list">
        <MemberList :members="members" />
    </div>
  </div>

</template>

<script>
import MemberList from './MemberList.vue'
import PageHeader from '../../PageHeader.vue'
import AnimatedComponent from '../../AnimatedComponent.vue'

export default { 
    name: "Team",
                                                   
    components: { 
        MemberList,
        PageHeader,
        AnimatedComponent,
    },

    data() {
        return {
            members: []
        }
    },

    created() {
        this.members = 
        [ 
            {
            name: "Elinor Onc",
            image: "https://res.cloudinary.com/dbdtfa9qb/image/upload/v1637750793/alphashift/me_glanul.jpg",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },

            {
            name: "Elinor Onc",
            image: "https://res.cloudinary.com/dbdtfa9qb/image/upload/v1637750793/alphashift/me_glanul.jpg",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },

            {
            name: "Elinor Onc",
            image: "https://res.cloudinary.com/dbdtfa9qb/image/upload/v1637750793/alphashift/me_glanul.jpg",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },

            {
            name: "Elinor Onc",
            image: "idk",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },
            {
            name: "Elinor Onc",
            image: "idk",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },
            {
            name: "Elinor Onc",
            image: "idk",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },
            {
            name: "Elinor Onc",
            image: "idk",
            position: "Web Developer",
            linkedIn: "https://www.linkedin.com/in/elinor-onc-66b250169/"
            },

        ]
    }
        

}
</script>

<style>

.container {
    display: flex;
    justify-content: space-evenly;
    align-items: flex-start;
    width: 100%;
    color: white;
    background: #171717;
}

#team-page {
    flex-direction: column;
    justify-content: space-evenly;
}

#list {
    display: flex;
    flex-direction: row;
    width: 80%;
    flex-wrap: wrap;
    align-self: center;
}

#header-container {
    align-self: center;
    width: 85%;
    margin: 70px;
}

@media (max-width: 600px){
  #list {
    flex-direction: column;
    justify-content: center;
    /* overflow: hidden; */
  }
}

</style>