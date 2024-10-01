
<template>
  <div>
    <h1>Count: {{count}}</h1>
    <CountChildren @increase="handleIncrease"/>
  </div>
</template>

<script setup>
import CountChildren from "./CountChildren.vue"
import { ref } from "vue"

const count = ref(0)

function handleIncrease(){
  count.value += 1
}
</script>

<style>
</style>
