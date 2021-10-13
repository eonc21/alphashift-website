<template>

  <div class="page">
    <div class="view-container">
      <Landing />
    </div>

    <div class="view-container">
      <WhoAreWe />
    </div>

    <div class="view-container">
      <WhatWeDo />
    </div>

    <div class="view-container">
      <OurServices />
    </div>

    <div id="fit-content" class="view-container">
      <MoreServices />
    </div>

    <div class="view-container">
      <ConsultingProcess />
    </div>

    <div class="view-container">
      <Conclusion />
    </div>

  </div>
  <!-- <h1>HELLO FROM VUEJS.</h1> -->
</template>


<script>
// import Vue from 'vue';
// import VueCarousel from 'vue-carousel';
import Landing from "./components/pages/Landing.vue"
import WhoAreWe from "./components/pages/WhoAreWe.vue"
import WhatWeDo from "./components/pages/WhatWeDo.vue"
import OurServices from "./components/pages/OurServices.vue"
import ConsultingProcess from "./components/pages/ConsultingProcess.vue"
import Conclusion from "./components/pages/Conclusion.vue"
import MoreServices from "./components/pages/MoreServices.vue"

// Vue.use(VueCarousel);

export default {
  name: 'App',
  components: {
    Landing,
    WhoAreWe, 
    WhatWeDo,
    OurServices,
    ConsultingProcess,
    Conclusion,
    MoreServices,

  }
}
</script>

<style>

html{
    scroll-behavior:smooth;

}
body {
  padding: 0;
  margin: 0;
  border: 0;
  overflow-x: auto;
  /* display: flex; */
}

body::-webkit-scrollbar {
  width: 13px;    
}
body::-webkit-scrollbar-track {
  background: #242424;      
}
body::-webkit-scrollbar-thumb {
  background-color: #8c2121f1;   
  border-radius: 20px;       
  border: 1px solid #242424;
}

#app {
  text-align: center;

}

.page {
  width: 100%;
  height: fit-content;
  scroll-behavior: smooth;

 
}

.view-container {
  height: 100vh;
  width: 100vw;
  max-width: 100%;

}

#fit-content {
  height: fit-content;
}

@media (max-width: 1000px){
  .view-container {
    height: fit-content;
    max-width: 100vw;
    /* overflow: hidden; */
  }
}

</style>
