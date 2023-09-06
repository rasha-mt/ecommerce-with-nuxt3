<template>
  <ProductDetails :product="product"></ProductDetails>
  <!--  <div>-->
  <!--    <p>Product details for {{ product.id }}</p>-->
  <!--    <p>-->
  <!--      {{ product.title }}-->

  <!--    </p>-->
  <!--  </div>-->
</template>

<script setup>
const {productId} = useRoute().params
definePageMeta({
  layout: 'products',
})

const {data: product} = await useFetch("https://fakestoreapi.com/products/" + productId, {key: productId})
if (!product.value) {
  throw createError({statusCode: 404, statusMessage: "Product not found", fatal: true})
}

</script>

<style scoped>

</style>