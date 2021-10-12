<template>
  <div class="form">
    <form @submit.prevent="sendEmail">
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
      <div class='checkboxes'>
          <input class="box" id="applicant" type="checkbox" value="applicant" name="apply" v-model="checkedBoxes"/>
          <label for="applicant" class="checkbox">I want to work at AlphaShift.</label>


         
          <input class="box" id="customer" type="checkbox" value="customer" name="customer" v-model="checkedBoxes"/>
           <label for="customer" class="checkbox">I want to be a customer.</label>
        
      </div>     
     

      <TextInput
        name="message"
        type="text"
        label="Notes:"
        placeholder="Your thoughts"
      />
      <br>
                <!-- <input type="submit" value="Send"> -->

      <Button :buttonClick="sendEmail"
      text="SUBMIT FORM" :type="submit"/>


    </form>
  </div>
  
</template>

<script>
// import {  Field } from 'vee-validate';
import TextInput from './TextInput.vue'
import Button from './Button.vue'
import emailjs from 'emailjs-com';
// let globalPayload = {}

export default {

  

    name: 'Contact',
  components: {
    // Form,
    // Field,
    Button,
    TextInput,
  },

  data() {
    return {
      checkedBoxes: [],
      name: '',
      email: '',
      message: ''
    }
  },

  methods: {

     async getFormValues (submitEvent) {
      return {

        from_email: submitEvent.target.email.value,
        from_name: submitEvent.target.name.value,
        user_title: this.checkedBoxes,
        user_message: submitEvent.target.message.value,
      }
    },


    async sendEmail(submitEvent) {
      alert(submitEvent.target.email)
            submitEvent.preventDefault();

      let payload =  await this.getFormValues(submitEvent)
    //   alert("payload")
      let validEmail = await this.validateEmail(submitEvent.target.email.value)
      let validNameAndMessage = await this.validateText(submitEvent.target.name.value, 
                            submitEvent.target.message.value)


      try {
        if (validEmail && validNameAndMessage) {
          emailjs.send('service_bjn1xnj', 'template_klkrcgq', payload,
            'user_qK5SJr6uQBEQWxZq1lBVZ', {
              name: this.name,
              email: this.email,
              message: this.message
        })
        } else {
          alert("Do not leave any inputs empty and make sure you do not use numbers and symbols in your name.")
        }
        

      } catch(error) {
          console.log({error})
      }
      // Reset form field
      this.name = ''
      this.email = ''
      this.message = ''
    },

    // onSubmit(values) {
    //   console.log(JSON.stringify(values, null, 2));
    // },
    async validateEmail(value) {
      // if the field is empty
      if (!value) {
        return false;
      }
      // if the field is not a valid email
      const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
      if (!regex.test(value)) {
        return false;
      }
      // All is good
      return true;
    },

    async validateText(name, message) {
      const regex  = /^[a-zA-Z\s]*$/;  
      console.log(name)

      if (regex.test(name) && name && message) {
        console.log("shits good")
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
    margin: 50px 0;
    width: 100%;
    height:550px;
    /* margin:auto; */
    font-family: "Poppins", sans-serif;
    /* color: rgba(255, 255, 255, 0.856); */
    /* border: 1px solid red; */
}
.checkbox {
  display: flex;
  width: 50%;
  /* align-self: center; */
  justify-content: center;
}

.box {
  margin-right: 20px;
  
  /* width: 80px; */
}

input[type=checkbox] {
    transform: scale(1.6);
}


.checkboxes {
  display: flex;
  justify-content: space-between;
  /* margin-bottom: 40px; */
  height: 75px;
  text-align: center;
  align-items: center;
  width: 90%;
  align-self: center;
  font-size: 1.5vw;
}

input {
  display: flex;
  /* width: 100%; */
  align-self: center;
  text-align: center;

}



button {
  width: 20%;
  margin: auto;
  align-self: center;
}

</style>