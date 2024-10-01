<template>
  <div class="container">
    <h2>Quản lý Nhân viên</h2>
    <button class="add-employee-btn" @click="openAddForm">+ Thêm mới nhân viên</button>
    <table class="employee-table">
      <thead>
        <tr>
          <th>STT</th>
          <th>Tên</th>
          <th>Giới tính</th>
          <th>Ngày sinh</th>
          <th>Email</th>
          <th>Địa chỉ</th>
          <th>Hành động</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(employee, index) in employees" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ employee.name }}</td>
          <td>{{ employee.gender }}</td>
          <td>{{ employee.dob }}</td>
          <td>{{ employee.email }}</td>
          <td>{{ employee.address }}</td>
          <td class="action">
            <button class="edit-btn" @click="openEditForm(index)">✏️</button>
            <button class="delete-btn" @click="confirmDeleteEmployee(index)">🗑️</button>
          </td>
        </tr>
      </tbody>
    </table>

    <employee-form
      v-if="showForm"
      :employee="editingEmployee"
      :edit-mode="editMode"
      @close="showForm = false"
      @save-employee="saveEmployee"
    ></employee-form>

    <delete-modal
      v-if="showDeleteModal"
      @delete="deleteEmployee"
      @close="showDeleteModal = false"
    ></delete-modal>
  </div>
</template>

<script>
import EmployeeForm from './components/ModalAdd.vue';
import DeleteModal from './components/ModalDelete.vue';

export default {
  components: {
    EmployeeForm,
    DeleteModal
  },
  data() {
    return {
      showForm: false,
      showDeleteModal: false,
      editMode: false,
      employees: [],
      editingEmployee: null,
      editingIndex: null,
      employeeToDeleteIndex: null
    };
  },
  methods: {
    openAddForm() {
      this.editMode = false;
      this.editingEmployee = null;
      this.showForm = true;
    },
    openEditForm(index) {
      this.editMode = true;
      this.editingEmployee = { ...this.employees[index] };
      this.editingIndex = index;
      this.showForm = true;
    },
    confirmDeleteEmployee(index) {
      this.employeeToDeleteIndex = index;
      this.showDeleteModal = true;
    },
    deleteEmployee() {
      this.employees.splice(this.employeeToDeleteIndex, 1);
      this.showDeleteModal = false;
    },
    saveEmployee(employee) {
      if (this.editMode) {
        this.employees.splice(this.editingIndex, 1, employee);
      } else {
        this.employees.push(employee);
      }
      this.showForm = false;
    }
  }
};
</script>

<style scoped>
.container {
  margin: 20px auto;
  width: 1000px;
  font-family: Arial, sans-serif;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
}

.add-employee-btn {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 15px;
  margin-bottom: 20px;
  cursor: pointer;
  border-radius: 5px;
}

.employee-table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
}

.employee-table th, .employee-table td {
  padding: 10px;
  text-align: center;
  border: 1px solid #ddd;
}

.edit-btn {
  background-color: #ffc107;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  margin-right: 5px;
  border-radius: 5px;
}

.delete-btn {
  background-color: #dc3545;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  border-radius: 5px;
}

.edit-btn, .delete-btn {
  color: white;
}

.action {
  display: flex;
}
</style>
