<template>
    <div class="register-form">
      <h2>Đăng ký tài khoản</h2>
      <form @submit.prevent="handleSubmit">
        <div>
          <label for="name">Tên sinh viên:</label>
          <input type="text" id="name" v-model="studentName" />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" />
        </div>
        <div>
          <label for="password">Mật khẩu:</label>
          <input type="password" id="password" v-model="password" />
        </div>
        <div>
          <label for="address">Địa chỉ:</label>
          <input type="text" id="address" v-model="address" />
        </div>
        <button type="submit">Đăng ký</button>
      </form>
      <p v-if="message">{{ message }}</p>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        studentName: '',
        email: '',
        password: '',
        address: '',
        message: '',
        registeredEmails: [], // Mảng để lưu trữ email đã đăng ký
      };
    },
    created() {
      // Lấy email đã đăng ký từ localStorage
      this.registeredEmails = JSON.parse(localStorage.getItem('registeredEmails')) || [];
    },
    methods: {
      handleSubmit() {
        // Kiểm tra các trường không được để trống
        if (!this.studentName || !this.email || !this.password) {
          this.message = 'Tên sinh viên, Email và Mật khẩu không được để trống';
          return;
        }
  
        // Kiểm tra email không được trùng
        if (this.registeredEmails.includes(this.email)) {
          this.message = 'Email đã được đăng ký';
          return;
        }
  
        // Lưu thông tin vào localStorage
        const userData = {
          studentName: this.studentName,
          email: this.email,
          password: this.password,
          address: this.address,
        };
  
        // Thêm email vào mảng đã đăng ký
        this.registeredEmails.push(this.email);
        localStorage.setItem('registeredEmails', JSON.stringify(this.registeredEmails));
        localStorage.setItem(this.email, JSON.stringify(userData));
  
        // Xóa hết các giá trị trong ô input
        this.studentName = '';
        this.email = '';
        this.password = '';
        this.address = '';
  
        // Hiển thị thông báo thành công
        this.message = 'Đăng ký tài khoản thành công';
  
        // Focus vào ô input Tên sinh viên
        this.$nextTick(() => {
          this.$refs.nameInput.focus();
        });
      },
    },
  };
</script>
<style scoped>
  .register-form {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  .register-form div {
    margin-bottom: 15px;
  }
  
  .register-form label {
    display: block;
    margin-bottom: 5px;
  }
  
  .register-form input {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
  }
  
  .register-form button {
    padding: 10px 15px;
  }
</style>
  