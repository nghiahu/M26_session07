<script setup>
  import ChildrenComponentVue from "./components/ChildrenComponent.vue"
  import ParentComponentVue from "./components/ParentComponent.vue"
  import ProductParentVue from "./components/ProductParent.vue"
  import CountParent from "./components/CountParent.vue"
  import TodoApp from "./components/TodoApp.vue"
  import ModalVue from "./components/Modal.vue"
  import { ref } from 'vue';
    const isModalOpen = ref(false);
    function closeModal(){
      isModalOpen.value = false
    }
    function openModal(){
      isModalOpen.value = true
    }
import CardVue from "./components/Card.vue"
import MessageParentVue from "./components/MessageParent.vue"
import ListUserVue from "./components/ListUser.vue"

</script>

<template>
  <div>Bài 1
  <ParentComponentVue/>
  Bài 2
  <ProductParentVue />
  Bài 3
  <CountParent/>
  Bài 4
  <TodoApp/>
  Bài 5
  <button @click="openModal">openModal</button>
  <ModalVue>
   <div v-if="isModalOpen" class="modal-overlay">
    <div class="modal-content">
      <div class="modal-header">
        <div>Thông báo từ hệ thống</div>
        <div class="close-btn" @click="closeModal">X</div>
      </div>
      <div class="modal-body">Đây là nội dung của modal. Bạn có thể đóng modal bằng cách nhấn vào nút Close</div>
      <button class="close-button" @click="closeModal">Close</button>
    </div>
  </div>
  </ModalVue>
  Bài 6
  <CardVue>
    <template #header>
      <span>Thông tin sản phẩm</span>
    </template> 
    <template #body>
      <span>Đây là mô tả ngắn gọn về sản phẩm này. Sản phẩm có các tính năng nổi bật và giả cả hợp lý.</span>
    </template> 
    <template #footer>
      <button class="footer">Xem chi tiết</button>
    </template> 
  </CardVue>
  Bài 7
  <MessageParentVue /> <br>
  Bài 8
  <ListUserVue/>
  </div>
</template>
  
<style scoped>
  .modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  width: 500px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  position: relative;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 18px;
  margin-bottom: 10px;
}

.close-btn {
  cursor: pointer;
  font-size: 18px;
  padding: 5px;
  border: none;
  background: none;
}

.modal-body {
  margin-bottom: 20px;
  font-size: 16px;
}

.close-button {
  background-color: #38393a;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  margin-left: 80%;
}   

.close-button:hover {
  background-color: #525455;
}
</style>
