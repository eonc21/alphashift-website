<template>
    <div class="container">
        <div id='text-container'>
            <animated-component>

            <PageHeader text="OUR SERVICES" />
            </animated-component>

            <animated-component>
                <ServiceList :services="services" />
            </animated-component>

        </div>
        <div class='btn'>
            <Button @click="buttonClick" text="LEARN MORE"/>
        </div>
        

        

    </div>
</template>

<script>
import ServiceList from '../ServiceList.vue'
import PageHeader from '../PageHeader.vue'
import Button from '../Button.vue'
import AnimatedComponent from '../AnimatedComponent.vue'

export default {

        name: 'OurServices',

        components: {
            ServiceList,
            PageHeader,
            Button,
            AnimatedComponent,
        },

        methods: {
            buttonClick() {
                alert('Learn more')
            }
        },

        data() {
            return {
                services: []
            }
        },

        created() {
            this.services = [
            {
                id: 1,
                text: `Data & AI Strategy Consulting`,
                description: `Validate the viability of implementing AI software 
                in your organization and make the shift from tactical AI 
                decision-making to a more strategic business plan.`,
                picture: "https://res.cloudinary.com/gromceri-test/image/upload/v1633645671/AlphaShift/strategy_nbvmo5.png"
            },

            {
                id: 2,
                text: `Data Analytics & Management`,
                description: `Validate the viability of implementing AI 
                software in your organization and make the shift from tactical
                 AI decision-making to a more strategic business plan.`,
                 picture: "https://res.cloudinary.com/gromceri-test/image/upload/v1633646073/AlphaShift/graph-white_m745jd.png"
            },

            {
                id: 3,
                text: `AI & ML Implementation`,
                description: `Companies should pay special attention to how
                 machine learning simplifies and speeds up implementation 
                 when incorporating intelligence into their infrastructure.`,
                 picture: "https://res.cloudinary.com/gromceri-test/image/upload/v1633645102/AlphaShift/aiml_bpgazl.png"
            },
            ]
        }
                
    }
</script>

<style scoped>

.container {
     display: flex;
    justify-content: space-evenly;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;
    height: 100vh;
    background: #171717;
}

.btn {
    display: flex;
    justify-content: center;
    align-self: center;
    width:20%;
}

#text-container {
    width: 85%;
    height: 70%;
    display: flex;
    align-self: center;
    justify-content:flex-start;
    flex-direction: column;
}

</style>