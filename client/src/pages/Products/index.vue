<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import { ref } from 'vue'
import { getAll, type Product } from '@/models/products'
import ProductCard from '@/components/ProductCard.vue'

const products = ref<Product[]>([])
products.value = getAll().data
</script>

<template>
  <div class="shelf">
    <ProductCard v-for="product in products" :key="product.id" :product="product" />
  </div>
</template>

<style scoped>
.shelf {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}
.shelf .box {
  width: 300px;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}
</style>
