<template>
  <div class="border border-red-500 rounded-lg shadow-md max-w-xs mx-auto">
    <div class="bg-gray-100 py-2 px-4 rounded-t-lg">
      <slot name="header" />
    </div>
    <div class="p-4">
      <slot name="body" />
    </div>
    <div class="card-footer bg-gray-100 py-2 px-4 rounded-b-lg">
      <slot name="footer" />
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComp",
};
</script>

<style scoped>
.card-wrapper {
  /* Adjust the desired width */
  max-width: 300px;
  /* Center the card horizontally */
  margin: 0 auto;
}
</style>
