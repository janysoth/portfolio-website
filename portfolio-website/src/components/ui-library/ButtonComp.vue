<template>
  <div>
    <button class="px-4 py-2 font-semibold text-white rounded-md hover:opacity-95 focus:outline-none mt-2 mb-2" :class="{
      [`bg-${color}-500`]: color,
    }" @click="onButtonClick">
      {{ buttonText }}
    </button>
  </div>
</template>

<script>
export default {
  name: "ButtonComp",
  props: {
    buttonText: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      default: "blue",
    },
  },
  methods: {
    onButtonClick() {
      this.$emit("button-clicked");
    },
  },
};
</script>

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

<!-- <script setup>
import { ref } from "vue";

// Define a ref to track the message state
const message = ref("");

// Function to display the message
const displayMessage = () => {
  message.value = "Button clicked!";
};
</script> -->
