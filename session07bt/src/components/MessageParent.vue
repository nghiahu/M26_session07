<template>
  <MessageChildren @messageSent="handelSeenMessage"/>
</template>

<script setup>
    import MessageChildren  from "./MessageChildren.vue"
    function handelSeenMessage(msg){
        alert(msg)
    }
</script>

<style>

</style>