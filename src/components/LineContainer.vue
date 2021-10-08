<template>
    <div id='middle-container'>
        <div class='half'>
            <div class='horizontal'></div>
             <div class="point"></div>
        </div>

        <div class='half'>
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

</style>