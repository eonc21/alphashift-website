<template>
    <div id='main-container'>
        <ProcessBox title="UNDERSTANDING THE PROBLEM" 
        content="Is a data solution suitable?"/>
        <div id=line-container>
            <div id='line'>
            </div>
             <div class="point"></div>
        </div>
        
        <ProcessBox title="UNDERSTANDING THE PROBLEM" 
        content="Is a data solution suitable?"/>


    </div>
</template>

<script>
import ProcessBox from '../components/ProcessBox.vue'
    export default {
        name: 'ProcessContainer',
        props: {
            titles: Array,
            contents: Array,
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
    color: white;
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


.point {
    
    display: flex;
    align-self: center;
    
}
</style>