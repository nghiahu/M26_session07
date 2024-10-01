<template>
  <div class="modal">
    <div class="modal-content">
      <span class="close-btn" @click="$emit('close')">&times;</span>
      <h3>{{ editMode ? "Chỉnh sửa nhân viên" : "Thêm mới nhân viên" }}</h3>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Tên</label>
          <input type="text" id="name" v-model="localEmployee.name" required />
        </div>
        <div class="form-group">
          <label for="gender">Giới tính</label>
          <select id="gender" v-model="localEmployee.gender" required>
            <option value="">Chọn giới tính</option>
            <option value="Nam">Nam</option>
            <option value="Nữ">Nữ</option>
          </select>
        </div>
        <div class="form-group">
          <label for="dob">Ngày sinh</label>
          <input type="date" id="dob" v-model="localEmployee.dob" required />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="localEmployee.email" required />
        </div>
        <div class="form-group">
          <label for="address">Địa chỉ</label>
          <textarea id="address" v-model="localEmployee.address" required></textarea>
        </div>
        <button type="submit" class="submit-btn">{{ editMode ? "Cập nhật" : "Thêm nhân viên" }}</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    employee: {
      type: Object,
      default: () => null
    },
    editMode: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      localEmployee: this.employee
        ? { ...this.employee }
        : {
            
            name: "",
            gender: "",
            dob: "",
            email: "",
            address: ""
          }
    };
  },
  methods: {
    submitForm() {
      this.$emit("save-employee", this.localEmployee);
    }
  }
};
</script>

<style scoped>
.modal {
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

.modal-content {
  background-color: white;
  padding: 20px;
  width: 500px;
  border-radius: 5px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
}

.close-btn {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  cursor: pointer;
  position: absolute;
  right: 20px;
  top: 10px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}

.submit-btn {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  border-radius: 5px;
}
</style>
