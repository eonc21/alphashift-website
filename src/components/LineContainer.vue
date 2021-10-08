<template>
    <div id='middle-container'>
        <div class='horizontal'>

        </div>

         <div class='horizontal bottom'>

        
        </div>
    </div>
</template>

<script>
    export default {
        name: 'LineContainer'
        
    }
</script>

<style scoped>

#middle-container {
    display: flex;
    width: 45%;
    height: 100%;
    flex-direction: column;
    justify-content: space-between;
    /* border: 1px solid blue; */
}

.horizontal {
    display: flex;
    width: 100%;
    height: 100px;
    border-bottom: 1px solid rgb(255, 255, 255);
}

.bottom {
    border-bottom: 0;

    border-top: 1px solid rgb(255, 255, 255);
    
    

}

</style>