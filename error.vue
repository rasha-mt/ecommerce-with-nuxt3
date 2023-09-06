<template>
  <div class="max-w-2xl mx-auto py-8 my-10 card text-center">
    <p class="font-bold text-6xl"> {{ error.statusCode }}</p>
    <p class="text-4xl mt-6"> Ooops....</p>
    <p class="text-base mt-6"> {{ error.statusMessage }}</p>
    <button class="btn mt-6" @click="handleError"> back to home</button>

  </div>

</template>

<script setup>
defineProps(['error'])
const handleError = () => clearError({redirect: '/'})
</script>

<style scoped>

</style>