<template>
  <div id='conclusion-page'>
      <PageHeader text="INTERESTED? CONTACT US." />
      <div id='form-container'>
          <Contact />
      </div>
      
  </div>
  <footer>
            THIS IS THE FOOTER
      </footer>
</template>

<script>
import Contact from '../Contact.vue'
import PageHeader from '../PageHeader.vue'

export default {

    name: 'Conclusion',

    components: {
        PageHeader,
        Contact,

    },

    props: {

    },


}
</script>

<style>

#conclusion-page {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background-color: #171717;
    color: rgba(255, 255, 255, 0.856);
}

#form-container {
    width: 60%;
    height: 500px;
    border: 1px solid pink;
    justify-content: center;

}

footer {
    flex-shrink: 0;
    background-color: black;

    width: 100%;
    height: 300px;
}

</style>