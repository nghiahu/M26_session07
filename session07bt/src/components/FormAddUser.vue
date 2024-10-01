<template>
  <div class="form-container">
    <div class="form-box">
      <h2>Form Add User</h2>
      <div>
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" v-model="name" placeholder="Enter your name" />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="email" placeholder="Enter your email" />
        </div>
        <div class="form-group">
          <label for="address">Address</label>
          <input type="text" id="address" v-model="address" placeholder="Enter your address" />
        </div>
        <button class="close-button" @click="handleClose">Close</button>
      </div>
    </div>
  </div>
</template>

<script setup>
    const emit = defineEmits(["close"])

    function handleClose(){
    emit("close")
    }
</script>

<style>
    .form-container {
  display: flex;
  align-items: center;
  margin: 15px;
}

.form-box {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  width: 300px;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 20px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

input {
  width: 100%;
  padding: 8px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

.close-button {
  background-color: red;
  color: white;
  border: none;
  padding: 10px;
  width: 100%;
  border-radius: 5px;
  cursor: pointer;
  text-align: center;
  font-size: 16px;
}

.close-button:hover {
  background-color: darkred;
}
</style>