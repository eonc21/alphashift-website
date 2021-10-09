<template>
  <Form @submit="onSubmit">
      <Field name="email" type="email" :rules="validateEmail"/>
            <ErrorMessage name="email" />

      <button>Sign up for newsletter</button>
    <!-- <div class="field">
        <label class="label">Inquiry Type</label>
        <div class="control">
            <div class="select">
            <select v-model="form.inquiry_type">
                <option disabled value="">Nothing selected</option>
                <option :key="option.value" v-for="option in options.inquiry" v-bind:value="option.value">
                {{ option.text }}
                </option>
            </select>
            </div>
        </div>
    </div> -->

    </Form>
</template>

<script>
import { Field, Form, ErrorMessage } from 'vee-validate';


export default {

    name: 'Contact',
  components: {
    Form,
    Field,
    ErrorMessage,
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

form {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    border: 1px solid red;
}

.field {
    display: flex;
    font-size: 2rem;
}

</style>