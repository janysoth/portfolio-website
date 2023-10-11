<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <button class="button" :class="buttonType" @click="onButtonClick">
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
    buttonType: {
      type: String,
      required: true,
    },
  },
  computed: {
    buttonTypes() {
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

<style lang="scss" scoped>
.button {
  color: #fff;
  font-weight: bold;
  padding: 0.5rem 1rem;
  border-radius: 100px;
  transition: background-color 0.3s;
}

.primary {
  background-color: #4299e1;

  &:hover {
    background-color: #1a365d;
    /* Darker blue on hover */
  }
}

.secondary {
  background-color: #f50911;

  &:hover {
    background-color: #f25b65;
    /* Change to the desired shade of blue for hover */
  }
}
</style>