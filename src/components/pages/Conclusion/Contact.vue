<template>
  <div class="form">
    
    <animated-component>  
    <form @submit.prevent="sendEmail">
      <p class="error" v-if="errors.length">
      Do not leave any inputs empty and make sure you do not use numbers and symbols in your name.
    </p>

    <p class="successful" v-if="success.length">
      Thank you for your submission.
    </p>
      <TextInput
        name="email"
        type="email"
        v-model="name"
        label="Email:"
        placeholder="Your email"
      />

      <TextInput
        name="name"
        type="text"
        label="Name:"
        placeholder="Your name"
      />
          
      <TextInput
        name="message"
        type="text"
        label="Notes:"
        placeholder="Your thoughts"
      />
      <div class='checkboxes'>
        <div class="box">
            <input id="applicant" type="checkbox" value="applicant" name="apply" v-model="checkedBoxes"/>
          <label for="applicant" class="checkbox">I want to work at AlphaShift.</label>
        </div>
          
        <div class="box">
            <input id="customer" type="checkbox" value="customer" name="customer" v-model="checkedBoxes"/>
           <label for="customer" class="checkbox">I want to be a customer.</label>
        </div>
      </div> 
      <br>
      <Button :buttonClick="sendEmail"
      text="SUBMIT FORM" :type="submit"/>
    </form>
    </animated-component>
  </div>
  
</template>

<script>
// import {  Field } from 'vee-validate';
import TextInput from '../../TextInput.vue'
import Button from '../../Button.vue'
import emailjs from 'emailjs-com';
import AnimatedComponent from '../../AnimatedComponent.vue'
// let globalPayload = {}

export default {

  name: 'Contact',
  components: {
    // Form,
    // Field,
    Button,
    TextInput,
    AnimatedComponent,
  },

  data() {
    return {
      errors: [],
      success: [],
      checkedBoxes: [],
      name: '',
      email: '',
      message: ''
    }
  },

  methods: {


  /**
   * Gets the values filled in by the user.
   */
  async getFormValues (submitEvent) {
    return {

      from_email: submitEvent.target.email.value,
      from_name: submitEvent.target.name.value,
      user_title: this.checkedBoxes,
      user_message: submitEvent.target.message.value,
    }
  },


  /**
   * Waits to get values of the form
   * and waits to validate the inputs, 
   * if they  are good an email gets 
   * sent to the company with the request.
   */
  async sendEmail(submitEvent) {
    submitEvent.preventDefault();

    let payload =  await this.getFormValues(submitEvent)
    let validEmail = await this.validateEmail(submitEvent.target.email.value)
    let validNameAndMessage = await this.validateText(submitEvent.target.name.value, 
                          submitEvent.target.message.value)

    // if all inputs are good, thank 
    // for submission and delete errors
    try {
      if (validEmail && validNameAndMessage) {
        this.errors = []
        this.success.push("Thank you for your submission.")

        // email service I used because no
        // time for backend
        emailjs.send('service_maq6egd', "template_7d0181u", payload,
          'user_Wv68JTifS2kYb9Ey9g1R0', {
            name: this.name,
            email: this.email,
            message: this.message
      })

      // if not, warn user about form 
      // requirements and clear successes
      } else {
        this.errors.push(`Do not leave any inputs empty 
          and make sure you do not use numbers 
          and symbols in your name.`)

        this.success = []
      }
    
    } catch(error) {
        console.log({error})
    }

    // Reset form field
    this.name = ''
    this.email = ''
    this.message = ''
  },


  /**
   * Checks to see if email fits
   * template/is empty using regex
   */
  async validateEmail(value) {

    if (!value) {
      return false;
    }

    const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
    if (!regex.test(value)) {
      return false;
    }

    return true;
  },


  /**
   * @param name the name of the user
   * @param message the notes of the user
   * 
   * Checks to see if text has any
   * symbols or numbers in it (assuming
   * that people won't be named like
   * Elon Musk's daughter)
   */
  async validateText(name, message) {
    const regex  = /^[a-zA-Z\s]*$/;  

    if (regex.test(name) && name && message) {
      return true;
    }

    return false;

  },
},

}
      

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

form {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    margin: 10px 0;
    width: 100%;
    height:550px;
    /* margin:auto; */
    font-family: "Poppins", sans-serif;
    /* color: rgba(255, 255, 255, 0.856); */
    /* border: 1px solid red; */
}
.checkbox {
  display: flex;
  width: 100%;
  /* align-self: center; */
  justify-content: center;
}

.box {
  display: flex;
  margin-right: 20px;
  
  /* width: 80px; */
}

input[type=checkbox] {
  background: #4273DE;
  color: #fff;
    transform: scale(1.6);
    margin-right: 20px;
    border-radius: 1px;
    outline: none;
    box-shadow: 0;
    background-color: rgba(0, 0, 0, 0);
    border: 0;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border: solid 1px rgba(255, 255, 255, 0.863);
    width: 15px;
    height: 13px;
  /* background: red; */

}


input[type=checkbox]:checked {
  background: rgb(116, 20, 20);
}

#applicant {

}


.checkboxes {
  display: flex;
  justify-content: space-between;
  /* margin-bottom: 40px; */
  height: 75px;
  text-align: center;
  align-items: center;
  width: 85%;
  align-self: center;
  font-size: 1.5vw;
}

input {
  display: flex;
  /* width: 100%; */
  align-self: center;
  text-align: center;

}

ul {
  display: flex;
  align-self: center;
}

.error, .successful {
      font-size: 1vw;
      color: rgb(255, 87, 87);
    }

    .successful {
      color: rgba(117, 216, 117, 0.849);
    }



button {
  width: 20%;
  margin: auto;
  align-self: center;
}

@media (max-width: 1000px) {
    form {
        width: 100%;
        height: 650px;
        justify-content: space-evenly;
        }

    .checkboxes {
      font-size: 2.25vw;
      width: 100%;
      justify-content: center;
      align-self: center;
    }

    .checkbox {
      width: 100%;
      align-self: flex-start;
      justify-content: flex-start;
      /* margin: 0; */
    }

    .box {
      width: 100%;
      justify-content: flex-start;

    }

    .error {
      display: flex;
      justify-content: left;
      font-size: 2.25vw;
    }

    .successful {
      display: flex;
      justify-content: left;
      font-size: 2.25vw;
    }

    input[type=checkbox] {
      /* margin: 0; */
    }

    


}

@media (max-width: 600px) {
  .form {
    height: 500px;
    
  }
    form {
        width: 80vw;
        margin: 50px 0;
        height: 70vh;
        justify-content: space-evenly;
        }

    .checkboxes {
      /* justify-content: flex-start; */
      flex-direction: column;
      align-self: flex-start;
      font-size: 4vw;
      justify-content: space-between;
      height: 70px;
      text-align: left;
    }

    .checkbox {
      width: 100%;
      align-self: flex-start;
      /* margin-bottom: 20px; */
      /* justify-content: spa; */
      margin: auto;
    }

    .box {
      width: 100%;
      justify-content: flex-start;
      align-items: flex-start;
      align-content: flex-start;
      margin: 0;
    }

    ul {
      /* display: block; */
      justify-content: flex-start;
    }

    .error {
      display: flex;
      justify-content: left;
      font-size: 3vw;
    }

    .successful {
      display: flex;
      justify-content: left;
      font-size: 3vw;
    }

    input[type=checkbox] {
      /* margin: 0; */
    }


}

</style>