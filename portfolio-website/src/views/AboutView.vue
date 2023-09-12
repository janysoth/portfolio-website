<template>
  <div>
    <CardComp class="mt-2">
      <template #header>
        <h2 class="text-xl">About Me:</h2>
      </template>
      <template #body>
        <div class="text-center flex flex-col items-center"> <!-- Center the content within the card's body -->
          <p>My name is Jonny Vorn Soth. I graduated from Austin High School in 2008. I'm currently learning Vue 3 with
            JavaScript for the last 6 months. </p>
        </div>
      </template>
      <template #footer>
        <p>Please contact me at janysoth@gmail.com if you have any questions...</p>
        <a href="#" class="text-blue-500 hover:underline">Read more</a>
      </template>
    </CardComp>
  </div>
</template>

<script>
import CardComp from "@/components/ui-library/CardComp.vue";

export default {
  components: {
    CardComp,
  },
}
</script>

<style></style>