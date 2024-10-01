<template>
<div>
  <button class="btnAdd" @click="openFrom">Add user</button>
  <FormAddUserVue v-if="isModel" @close="handleCloseFrom"/>
  </div>

</template>

<script setup>
    import { ref } from "vue";
import FormAddUserVue from "./FormAddUser.vue";
    const isModel = ref(false)
    function openFrom(){
        isModel.value = true
    }
    function handleCloseFrom(){
        isModel.value = false
    }
</script>

<style>
.btnAdd{
    padding: 10px;
    border-radius: 5px;
    border: none;
    background-color: rgb(55, 147, 217);
    color: white;
}
</style>