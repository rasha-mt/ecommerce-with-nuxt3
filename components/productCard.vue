<template>

  <!--
    This example requires some changes to your config:

    ```
    // tailwind.config.js
    module.exports = {
      // ...
      plugins: [
        // ...
        require('@tailwindcss/aspect-ratio'),
      ],
    }
    ```
  -->
  <div class="bg-white">
    <div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-8 lg:max-w-7xl lg:px-8 text-center">
      <h2 class="sr-only">Products</h2>


      <a href="#" class="group">
        <div class="aspect-h-1 aspect-w-1 w-full overflow-hidden rounded-lg xl:aspect-h-8 xl:aspect-w-7">
          <img :src="`${product.image}`" class="object-cover object-center group-hover:opacity-75 thumb" >
        </div>
        <p class="font-bold text-gray-500 m-4 truncate">{{ product.title }}</p>
        <NuxtLink :to="`/products/${product.id}`" ><p class="btn my-4">View Details</p></NuxtLink>
      </a>


      <!-- More products... -->

    </div>
  </div>

</template>

<script setup>
const {product} = defineProps(['product'])
</script>

<style scoped>
.thumb{
  max-height: 120px;
  margin: 0 auto;
}

</style>