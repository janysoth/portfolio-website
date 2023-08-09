<template>
  <div class="portfolio-view">
    <h1>This is a Portfolio Page</h1>
    <p>I'm currently learning JavaScript and Vue 3.</p>
    <div class="flex items-center mt-4 justify-center">
      <input
        v-if="!message"
        v-model="inputValue"
        class="border border-gray-300 px-2 py-2 rounded-md mr-2 w-64"
        placeholder="Enter Your Name Here..."
      />
      <ButtonComp
        v-if="!message"
        button-text="Submit"
        @button-clicked="handleButtonClick"
      />
    </div>
    <p>{{ message }}</p>
    <ButtonComp
      button-text="Clear Message"
      v-if="message"
      @button-clicked="removeMessage"
    />
    <!-- <button
      v-if="message"
      class="px-4 py-2 font-semibold text-white bg-red-500 rounded-md hover:opacity-95 focus:outline-none mt-2"
      @click="removeMessage"
    >
      Clear Message
    </button> -->
  </div>
</template>

<script>
import ButtonComp from "../../src/components/ui-library/ButtonComp.vue";

export default {
  components: {
    ButtonComp,
  },
  data() {
    return {
      message: "",
      inputValue: "",
    };
  },
  methods: {
    handleButtonClick() {
      // Update the message when the button is clicked
      this.message = `Hi, ${this.inputValue}. Hope you have a good day!`;
    },

    removeMessage() {
      this.message = ""; // Clear the message
      this.inputValue = "";
    },
  },
};
</script>
