<template>
  <div id="widget-container">
      <div class="half-widget" id="vertical">
          <h3>
              {{ widget.title }}
          </h3>

          <p id="text">
              {{ widget.text }}
          </p>
      </div>

      <div class="half-widget" id="image">
          <img :src="widget.image" />

      </div>

  </div>
</template>

<script>
export default {
    name: 'HorizontalWidget',

    props: {
        widget: Object,
    
    }

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

#widget-container {
    width: 90%;
    display: flex;
    font-family: "Poppins", sans-serif;
}

.half-widget {
    display: flex;
    flex-direction: column;
    justify-content: center;
    /* height: 40vh; */
    width: 50%;
}

img {
    align-self: center;
    object-fit: cover;
    border-radius: 5px;
  
}

h3 {
    font-size: 1.75vw;
    font-weight: 400;
}

#text {
    /* font-size: 1.25vw; */
    width: 90%;
    color: #868686;

    
}

@media (max-width: 600px) {

    #widget-container {
        flex-direction: column;
    }

    .half-widget {
        width: 90vw;
    }

    h3 {
        font-size: 8vw;
    }

    #text {
        font-size: 5vw;
    }

    img {
        /* height: 100px; */
    }
    
}

</style>