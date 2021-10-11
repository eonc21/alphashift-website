<template>
  <div class="form">
    <Form  @submit="onSubmit">
      <TextInput
        name="email"
        type="email"
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
        <Field v-slot="{ field }" name="apply" type="checkbox" :value="false">
          <label>
            <input type="checkbox" name="apply" v-bind="field" :value="false" />
             I want to work at AlphaShift.
          </label>
        </Field>
        <Field v-slot="{ field }" name="customer" type="checkbox" :value="false">
          <label>
            <input type="checkbox" name="customer" v-bind="field" :value="false" />
               I want to be a customer.
          </label>
        </Field>
      </div>     

      <TextInput
        name="message"
        type="text"
        label="Message:"
        placeholder="Your thoughts"
      />

      <Button text="SUBMIT"/>


    </Form>
  </div>
  
</template>

<script>
import { Form, Field } from 'vee-validate';
import TextInput from './TextInput.vue'
import Button from './Button.vue'


export default {

    name: 'Contact',
  components: {
    Form,
    Field,
    Button,
    TextInput,
  },

  methods: {
    onSubmit(values) {
      console.log(JSON.stringify(values, null, 2));
    },
    validateEmail(value) {
      // if the field is empty
      if (!value) {
        return 'This field is required';
      }
      // if the field is not a valid email
      const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
      if (!regex.test(value)) {
        return 'This field must be a valid email';
      }
      // All is good
      return true;
    },
  },

    // data() {
    //   return {
    //     options: {
    //     inquiry: [
    //       { value: 'feature', text: "Feature Request"},
    //       { value: 'bug', text: "Bug Report"},
    //     ]
    //   }
    // }
    //   }
    }
      

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,300;0,400;1,200;1,300&display=swap');

form {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    width: 100%;
    height:550px;
    margin:auto;
    font-family: "Poppins", sans-serif;
    /* color: rgba(255, 255, 255, 0.856); */
    /* border: 1px solid red; */
}
label {
  display: flex;
  /* width: 35%; */
}

.checkboxes {
  display: flex;
  justify-content: space-between;
  /* margin-bottom: 40px; */
  height: 75px;
  text-align: center;
  align-items: center;
  width: 75%;
  align-self: center;
  font-size: 1.5vw;
}

input {
  display: flex;
  /* width: 100%; */
  align-self: center;
  text-align: center;
  margin-right: 10px;

}

button {
  width: 20%;
  margin: auto;
  align-self: center;
}

</style>