<template>
  <div class="delete-modal">
    <div class="delete-modal-content">
      <p>Xác nhận xóa nhân viên</p>
      <p>Bạn có chắc chắn muốn xóa nhân viên này?</p>
      <button @click="confirmDelete">Xóa</button>
      <button @click="closeModal">Hủy</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean 
  },
  methods: {
    confirmDelete() {
      this.$emit('delete'); 
    },
    closeModal() {
      this.$emit('close'); 
    }
  }
};
</script>

<style scoped>
.delete-modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.delete-modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.delete-modal-content p {
  margin: 10px 0;
  font-size: 16px;
}

.delete-modal-content button {
  margin: 5px;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.delete-modal-content button:first-child {
  background-color: #dc3545;
  color: white;
}

.delete-modal-content button:last-child {
  background-color: #6c757d;
  color: white;
}
</style>
