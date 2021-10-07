<template>
    <div id='btn'>
        <text>
        LEARN MORE >

        </text>

    </div>
</template>

<script>
    export default {
        name: 'Button',
        
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400&display=swap');

#btn {
    display: flex;
    justify-content: center;
    color: rgba(255, 255, 255, 0.84);
    font-size: 1.75rem;
    font-weight: 400;
    letter-spacing: 2px;
    font-family: "Oswald", sans-serif;
    align-items: center;
    align-self: center;
    width: 80%;
    height: 100px;
    margin: 10px;
    border-radius: 10px;
    background: linear-gradient(90deg, rgba(0, 0, 0, 0.45) 0%, rgba(79, 25, 25, 0.215625) 52.08%, rgba(255, 31, 31, 0.261) 100%), #8F2626;
}


</style>