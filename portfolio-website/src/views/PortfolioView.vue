<template>
  <div class="portfolio-view">
    <h1>This is a Portfolio Page</h1>
    <p>I'm currently learning JavaScript and Vue 3.</p>
    <ButtonComp :button-text="buttonText" @button-clicked="handleButtonClick" />
    <p>{{ message }}</p>
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
  },
};
</script>
