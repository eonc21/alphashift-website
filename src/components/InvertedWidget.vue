<template>
  <div id="widget-container"> 

      <div class="half-widget">
          <img :src="widget.image" />

      </div>

      <div class="half-widget" id="vertical">
          <h3>
              {{ widget.title }}
          </h3>

          <p id="text">
              {{ widget.text }}
          </p>
      </div>

  </div>
</template>

<script>
export default {
    name: 'InvertedWidget',

    props: {
        widget: Object,
    
    }

}
</script>

<style>

#widget-container {
    display: flex;
}

.half-widget {
    width: 50%;
}

#text {
    font-size: 1.25vw;
}

img {
    width: 80%;
    object-fit: cover;
    /* height: 90%; */
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