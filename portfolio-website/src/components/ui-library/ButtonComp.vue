<template>
  <button
    :type="type"
    class="px-6 py-2 font-semibold text-white bg-blue-500 rounded-md hover:opacity-95 focus:outline-none"
  >
    <slot>Submit</slot>
  </button>
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

<script setup></script>
<style></style>
