<template>
  <ProductChildrenVue :propProduct="product"/>
</template>

<script setup>
import { reactive } from "vue";
import ProductChildrenVue from "./ProductChildren.vue";

    const product={
        id: 1,
        productName:"Bưởi ba roi",
        price:"12.000 đ",
        quantity: 10
    }
</script>

<style>

</style>