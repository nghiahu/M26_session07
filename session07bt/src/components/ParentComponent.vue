<template>
<div>
  <h1>Parent Company: {{data}}</h1>
  <ChildrenComponentVue :propsName="data"/>
</div>
</template>

<script setup>
    import {ref} from "vue"
    import ChildrenComponentVue from "./ChildrenComponent.vue"
    const data = ref("Rikkei Academy")
</script>

<style>

</style>