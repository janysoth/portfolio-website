<template>
  <div class="portfolio-view">
    <h1>This is a Portfolio Page</h1>
    <p>I'm currently learning JavaScript and Vue 3.</p>
    <div class="flex items-center mt-4 justify-center">
      <input v-if="!message" v-model="inputValue" class="border border-gray-300 px-2 py-2 rounded-md mr-2 w-64"
        placeholder="Enter Your Name Here..." />
      <ButtonComp v-if="!message" button-text="Submit" @button-clicked="handleButtonClick" color="blue" />
    </div>
    <p>{{ message }}</p>
    <ButtonComp button-text="Clear Message" v-if="message" @button-clicked="removeMessage" color="red" />
    <CardComp class="mt-2">
      <template #header>
        <h2 class="text-xl">Jonny Vorn Soth</h2>
      </template>
      <template #body>
        <div class="text-center flex flex-col items-center"> <!-- Center the content within the card's body -->
          <p>Here's Cambodia Flag</p>
          <img src="@/assets/cambodia-flag.png">
          <video controls autoplay loop class="mt-4">
            <source src="@/assets/cambodia-flag-animation.mp4" type="video/mp4">
          </video>
        </div>
      </template>
      <template #footer>
        <p>Card Footer with additional information.</p>
        <a href="#" class="text-blue-500 hover:underline">Read more</a>
      </template>
    </CardComp>
  </div>
</template>

<script>
/* eslint-disable */
/* prettier-ignore */
import CardComp from "@/components/ui-library/CardComp.vue";
import ButtonComp from "../../src/components/ui-library/ButtonComp.vue";

export default {
  components: {
    ButtonComp,
    CardComp,
  },

  data() {
    return {
      message: "",
      inputValue: "",
      color: "",
    };
  },

  methods: {
    handleButtonClick() {
      if (this.inputValue)
        // Update the message when the button is clicked
        this.message = `Hi, ${this.inputValue}. Hope you have a good day!`;
      else this.message = "Please Enter Your Name";
    },
    removeMessage() {
      this.message = ""; // Clear the message
      this.inputValue = "";
    },
  },
};
</script>
