<template>
  <button @click="hendleMessage">Send message</button>
</template>

<script setup>
    const emit = defineEmits(["messageSent"])
    function hendleMessage(){
        emit("messageSent","Thông báo từ Childrent component")
    }
</script>

<style>

</style>