<template>
  <div>
    <h1>Dữ liệu trong component con</h1>
    <div>Id: {{props.propProduct.id}}</div>
    <div>Product Name: {{props.propProduct.productName}}</div>
    <div>Price: {{props.propProduct.price}}</div>
    <div>Quantity: {{props.propProduct.quantity}}</div>
  </div>
</template>

<script setup>
    const props = defineProps(["propProduct"])
    console.log(props.propProduct);
    
</script>

<style>

</style>