<template>
    <div id='main-container'>
        <ProcessBox :title="titles[0]" :hasContent="isLeft"
        />
        <div id=line-container>
            <div v-if="isLeft" id='word'>NO.</div>
            <div id='line'>
            </div>
             <div class="point"></div>
        </div>
        
        <ProcessBox :title="titles[1]"
       />


    </div>
</template>

<script>
import ProcessBox from '../components/ProcessBox.vue'
    export default {
        name: 'ProcessContainer',
        props: {
            titles: Array,
            contents: Array,
            isLeft: Boolean,
        },

        components: {
            ProcessBox,
        }
        
    }
</script>

<style scoped>

#main-container {
    display: flex;
    /* border: 1px solid orange; */
    flex-direction: column;
    justify-content: space-between;
    align-self: center;
    width: 25%;
    height: 100%;
    color: rgba(255, 255, 255, 0.835);
}
.point {
    width: 0;
    height: 0;
    border-top: 8px solid rgba(255, 255, 255, 0.87);
    border-bottom: 8px solid transparent;
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    align-self: center;
}

#line-container {
    display: flex;
    flex-direction: column;
    width: 100%;
    /* align-self: center; */
    /* margin:auto; */
    height: 35%;
    justify-content: flex-start;
    align-content: center;
}

#line {
    height: 95%;
    width: 50%;
    border-right: 1px solid white;

}

#word {
    font-size: 1.75rem;
    margin-bottom: 20px;
}

.point {
    
    display: flex;
    align-self: center;
    
}

@media (max-width: 600px) {

    #main-container {
        width: 80vw;
        height: 600px;
        justify-content: center;
        align-self: flex-start;
    }

    #line-container {
        align-self: center;
        height: 20%;
    }

    #line {
        width: 50%;
    }

    #word {
        height: 0;
        width: 0;
        visibility: hidden;

    }
    
}



</style>