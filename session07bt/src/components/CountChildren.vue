<template>
  <div>
    <button @click="handleIncrease">Increment</button>
  </div>
</template>

<script setup>
const emit = defineEmits(["increase"])

function handleIncrease(){
  emit("increase")
}
</script>

<style>
</style>