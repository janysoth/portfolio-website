<template>
  <div>
    <button
      :type="type"
      class="px-6 py-2 font-semibold text-white bg-blue-500 rounded-md hover:opacity-95 focus:outline-none"
      @click="displayMessage"
    >
      <slot>Submit</slot>
    </button>
    <p v-if="message">{{ message }}</p>
  </div>
</template>

<!-- <script>
export default {
  name: "ButtonComp",
  props: {
    type: {
      type: String,
      default: "Submit",
    },
    buttonText: {
      type: String,
      default: "Click Me",
    },
  },
};
</script> -->

<script setup>
import { ref } from "vue";

// Define a ref to track the message state
const message = ref("");

// Function to display the message
const displayMessage = () => {
  message.value = "Button clicked!";
  // Replace the above line with your custom logic to display the message
  // For example, you can show an alert like this: alert('Button clicked!');
};
</script>
