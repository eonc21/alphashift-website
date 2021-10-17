<template>
    <nav>
        <div class="nav">
            <LinkList :navLinks="navLinks" />
        </div>
        
    </nav>
  
</template>

<script>
import LinkList from './LinkList.vue'
export default {

    name: 'NavBar',

    components: {
        LinkList,
    },

    data() {
            return {
                navLinks: []
            }
        },

        created() {
            this.navLinks = [
            {
                name: "About us",
                link: "who-we-are-page"
            },
            {
                name: "Our task",
                link: "what-are-we-page"
            },
            {
                name: "Services",
                link: "services-page"
            },
            {
                name: "Process",
                link: "page"
            },
            {
                name: "Contact us",
                link: "conclusion-page"
            },
            ]
        }

}
</script>

<style>

nav {
    display: flex;
    width: 100%;
    align-self: flex-start;
    justify-content: flex-end;
}

.nav {
    width: 50%;
    margin-right: 30px;
    display: flex;
    justify-content:space-evenly;
    flex-direction: row;
    align-self: flex-end;
    /* width: 80vw; */
}

@media (max-width: 1000px) {

    
    .nav {
        margin-right: 5%;
        width: 70%;
    } 
    
}

@media (max-width: 600px) {

    nav {
        justify-content: center;
    }
    .nav {
        flex-wrap: wrap;
        margin-right: 0;
        width: 90%;
    }
    
}





</style>