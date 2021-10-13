<template>
  <div
    class="TextInput"
    :class="{ 'has-error': !!errorMessage, success: meta.valid }"
  >
    <label :for="name">{{ label }}</label>
    <input
      :name="name"
      :id="name"
      :type="type"
      :value="inputValue"
      :placeholder="placeholder"
      @input="handleChange"
      @blur="handleBlur"
    />

    <p class="help-message" v-show="errorMessage || meta.valid">
      {{ errorMessage || successMessage }}
    </p>
  </div>
</template>

<script>
import { useField } from "vee-validate";

export default {
  props: {
    type: {
      type: String,
      default: "text",
    },
    value: {
      type: String,
      default: "",
    },
    name: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    successMessage: {
      type: String,
      default: "",
    },
    placeholder: {
      type: String,
      default: "",
    },
  },
  setup(props) {
    // we don't provide any rules here because we are using form-level validation
    // https://vee-validate.logaretm.com/v4/guide/validation#form-level-validation
    const {
      value: inputValue,
      errorMessage,
      handleBlur,
      handleChange,
      meta,
    } = useField(props.name, undefined, {
      initialValue: props.value,
    });

    return {
      handleChange,
      handleBlur,
      errorMessage,
      inputValue,
      meta,
    };
  },
};
</script>

<style  scoped>
.TextInput {

display: flex;
height: 100px;
  width: 90%;
  align-self: center;
  justify-content: space-between;
  /* border: 1px solid seagreen; */
  text-align: center;
  font-size: 1.7vw;
  margin-bottom: 1%;

}

label {
  display: flex;
  align-self: center;
  margin-bottom: 4px;
  /* width: 30%; */
  justify-content: center;

}

input {
  border: 0.5px solid rgba(255, 255, 255, 0.856);
  padding: 15px 10px;
  background-color: #171717;
  width: 40vw;
  transition: border-color 0.3s ease-in-out, color 0.3s ease-in-out,
    background-color 0.3s ease-in-out;
  font-size: 1.5vw;

}


.help-message {
  position: absolute;
  bottom: calc(-1.5 * 1em);
  left: 0;
  margin: 0;
  font-size: 14px;
}

.TextInput.has-error input {
  background-color: var(--error-bg-color);
  color: var(--error-color);
}

.TextInput.has-error input:focus {
  border-color: var(--error-color);
}

.TextInput.has-error .help-message {
  color: var(--error-color);
}

.TextInput.success input {
  background-color: var(--success-bg-color);
  color: var(--success-color);
  /* border: var(seagreen); */
}

.TextInput.success input:focus {
  border-color: var(--success-color);
}

.TextInput.success .help-message {
  color: var(--success-color);
}

@media (max-width: 1000px) {
    .TextInput {
      width: 100%;
      font-size: 2.75vw;

    }

    input {
      width: 57vw;
      padding: 12px 10px;
      font-size: 2.75vw;
      font-family: "Poppins", sans-serif;
      border-radius: 0px;
      
    }

}

@media (max-width: 600px) {
    .TextInput {
      width: 100%;
      height: 8%;
      font-size: 4vw;

    }

    input {
      width: 57vw;
      padding: 12px 10px;
      font-size: 3.4vw;
      font-family: "Poppins", sans-serif;
      border-radius: 0px;
      
    }

}

</style>