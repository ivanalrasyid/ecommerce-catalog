<template>
  <section class="catagory-products">
    <div class="container">
      <CatagoryHeader :title="title" :tabs="tabs" />
      <div class="products">
        <SingleProduct
          v-for="(product, i) in products"
          :key="i"
          :product="product"
        />
      </div>
      <button class="btn">SEE ALL</button>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from "vue";
import CatagoryHeader from "./CatagoryHeader.vue";
import SingleProduct from "./SingleProduct.vue";
defineProps(["title", "products", "tabs"]);
</script>

<style scoped>
.catagory-products {
  margin-bottom: 100px;
}
.catagory-products .btn {
  height: 48px;
  background: #f8f8f8;
  border: 2px solid #f8f8f8;
  max-width: 100%;
  margin-top: 18px;
}
.products {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 30px;
}
@media (max-width: 969px) {
  .products {
    grid-template-columns: 1fr 1fr;
  }
}
@media (max-width: 400px) {
  .products {
    grid-template-columns: 1fr;
  }
}
</style>
