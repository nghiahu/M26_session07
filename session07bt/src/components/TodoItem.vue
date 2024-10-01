<template>
    <button @click="hendleDel">Delete</button>
</template>

<script setup>
    const emit = defineEmits(["delId"])
    function hendleDel(){
        emit("delId","1")
    }
</script>

<style>

</style>