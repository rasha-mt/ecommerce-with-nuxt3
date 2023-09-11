<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="product in products">
        <productCard :product="product"></productCard>
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: 'products'
})
const {data: products} = await useFetch("https://fakestoreapi.com/products");

useHead({
  title: 'Nuxt Dojo | Merch',
  meta: [{
    name: 'description', content: 'products yoo'
  }]

})

</script>