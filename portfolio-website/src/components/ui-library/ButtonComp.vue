<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <button class="px-4 py-2 font-semibold text-white rounded-md hover:opacity-95 focus:outline-none mt-2 mb-2"
      :class="buttonColors" @click="onButtonClick">
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
      required: true,
    },
  },
  computed: {
    buttonColors() {
      // Dynamically compute the button's background color based on the 'color' prop
      return {
        "bg-blue-500": this.color === "primary",
        "bg-red-500": this.color === "secondary",
      };
    },
  },
  methods: {
    onButtonClick() {
      this.$emit("button-clicked");
    },
  },
};
</script>
