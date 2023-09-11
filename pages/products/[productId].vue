<template>
  <div>
    <Head>
      <Title> {{product.title}}</Title>
      <Meta name="description" :content="product.description"></Meta>
    </Head>
    <ProductDetails :product="product"></ProductDetails>
  </div>

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