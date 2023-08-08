<template>
  <div class="portfolio-view">
    <h1>This is a Portfolio Page</h1>
    <p>I'm currently learning JavaScript and Vue 3.</p>
    <ButtonComp
      v-if="!message"
      :button-text="buttonText"
      @button-clicked="handleButtonClick"
    />
    <p>{{ message }}</p>
    <button
      v-if="message"
      class="px-4 py-2 font-semibold text-white bg-red-500 rounded-md hover:opacity-95 focus:outline-none mt-2"
      @click="removeMessage"
    >
      Clear Message
    </button>
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
      buttonText: "Click Here",
      message: "",
    };
  },
  methods: {
    handleButtonClick() {
      // Update the message when the button is clicked
      this.message = "You have clicked a button!";
    },

    removeMessage() {
      this.message = ""; // Clear the message
    },
  },
};
</script>
