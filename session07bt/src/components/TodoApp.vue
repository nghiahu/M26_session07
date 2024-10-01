<template>
  <div>
    Id to delete: {{idDel}} <br>
    <TodoItem @delId="chIdDel"/>
  </div>
</template>

<script setup>
    import { ref } from "vue";
import TodoItem from "./TodoItem.vue"
    const idDel = ref("");
    function chIdDel(id){
        idDel.value = id
    }
</script>

<style>

</style>