<template>
  <div class="outlet">
    <div class="header"><slot name="header"></slot></div>
    <div class="body"><slot name="body"></slot></div>
        <slot name="footer"></slot>
  </div>
</template>

<script>

</script>

<style>
.outlet{
    border: 1px solid black;
    width: 500px;
    height: 170px;
    margin: 10px;
    padding: 15px;
    border-radius: 5px;
}
.header{
    font-weight: bold;
    font-size: 21px;
    margin-bottom: 10px;
}
.footer{
    padding: 8px;
    margin-top: 10px;
    width: 140px;
    border: none;
    background-color: rgb(60, 127, 222);
    color: white;
}
</style>