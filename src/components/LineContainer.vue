<template>
    <div id='middle-container'>
        <div class='half'>
            <div class='word'>YES.</div>
            <div class='horizontal'></div>
             <div class="point"></div>
        </div>

        <div id='text'>
           <p>
               OUR PROCESS.
           </p>
        </div>

        <div id='second-arrow' class='half'>
             <div class="point left"></div>
            <div class='horizontal'></div>

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
    color: white;
    /* border: 1px solid blue; */
}

.horizontal {
    display: flex;
    width: 100%;
    height: 100px;
    border-bottom: 1px solid rgb(255, 255, 255);
}

.point {
width: 0;
  height: 0;
  border-top: 8px solid transparent;
  border-bottom: 8px solid transparent;
  border-left: 8px solid rgba(255, 255, 255, 0.87);
  align-self: center;
}

.left {
  border-right: 8px solid rgba(255, 255, 255, 0.87);
  border-left: 0;
}



.half {
    display: flex;
    justify-content: center;
    height: 200px;
}

.word {
    align-self: center;
    margin-right: 25px;
    font-size: 1.75rem;
}

#text {
    font-size: 2.5vw;
    width: 80%;
    align-self: center;
    font-weight: 300;
    color: rgba(255, 255, 255, 0.8);
}

@media (max-width: 600px) {
   
    .horizontal {
        /* /* border-left: 1px solid white; */
        border-bottom: 0; 
        /* width: 0%;  */
        
    }

    #second-arrow, .word, #text {
        width: 0;
        height: 0;
        visibility: hidden;
    }

    .half {
        height: 100%;
        width: 50%;
        border-right: 1px solid white;
        text-align: center;
}


    

    .point {
       
           border-top: 8px solid rgba(255, 255, 255, 0.87);
    border-bottom: 8px solid transparent;
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    
    align-self: flex-end;
    

    }


    #middle-container {
        height: 45px;
    
    
    }
    
    

}

</style>