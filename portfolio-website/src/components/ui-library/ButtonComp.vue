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

  &:hover {
    opacity: 0.5;
  }
}

.primary {
  background-color: #4299e1;
}

.secondary {
  background-color: #f50911;
}
</style>