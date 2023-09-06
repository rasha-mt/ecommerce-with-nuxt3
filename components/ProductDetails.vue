<template>
  <!--
    This example requires some changes to your config:

    ```
    // tailwind.config.js
    module.exports = {
      // ...
      theme: {
        extend: {
          gridTemplateRows: {
            '[auto,auto,1fr]': 'auto auto 1fr',
          },
        },
      },
      plugins: [
        // ...
        require('@tailwindcss/aspect-ratio'),
      ],
    }
    ```
  -->
  <div class="bg-white">
    <!-- Product info -->
    <div
        class="mx-auto max-w-full px-4 pb-16 pt-10 sm:px-6 lg:grid lg:max-w-full lg:grid-cols-2 lg:grid-rows-[auto,auto,1fr]  lg:gap-x-8 lg:px-8 lg:pb-24 lg:pt-16">
      <div class="mt-6 max-w-2xl sm:px-6 lg:grid lg:max-w-xl  lg:pr-8 mr-12">
        <div class="aspect-h-5 aspect-w-4 lg:aspect-h-4 lg:aspect-w-3 sm:overflow-hidden sm:rounded-lg">
          <img :src="`${product.image}`" class="h-full w-full object-cover object-center">
        </div>
      </div>

      <div class="mx-auto mt-6 max-w-full sm:px-6">
        <div class="lg:col-span-2">
          <h1 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">{{ product.title }}</h1>
        </div>

        <div class="py-10 lg:col-span-2 lg:col-start-1  lg:pb-16 lg:pr-8 lg:pt-6">
          <!-- Description and details -->
          <div>
            <div class="my-7"> Price - ${{ product.price }}</div>
            <div class="space-y-6">
              <h3 class="font-bold border-b-2 my-7">Product description</h3>
              <p class="text-base text-gray-900"> {{ product.description }}</p>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>

</template>

<script setup>
const {product} = defineProps(['product'])
</script>

<style scoped>

</style>