<template>
    <div class="exercise08">
      <h2>Đăng Ký Tài Khoản Mới</h2>
      <form @submit.prevent="register">
        <div class="form-group">
          <label for="name">Tên:</label>
          <input
            type="text"
            id="name"
            v-model.trim="user.name"
            required
            placeholder="Nhập tên của bạn"
          />
        </div>
  
        <div class="form-group">
          <label for="email">Email:</label>
          <input
            type="email"
            id="email"
            v-model.trim="user.email"
            required
            placeholder="Nhập email của bạn"
          />
        </div>
  
        <div class="form-group">
          <label for="password">Mật khẩu:</label>
          <input
            type="password"
            id="password"
            v-model="user.password"
            required
            minlength="6"
            placeholder="Nhập mật khẩu"
          />
        </div>
  
        <div class="form-group">
          <label for="confirmPassword">Nhập lại mật khẩu:</label>
          <input
            type="password"
            id="confirmPassword"
            v-model="user.confirmPassword"
            required
            minlength="6"
            placeholder="Nhập lại mật khẩu"
          />
        </div>
  
        <button type="submit" class="btn">Đăng ký</button>
      </form>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise08',
    data() {
      return {
        user: {
          name: '',
          email: '',
          password: '',
          confirmPassword: ''
        }
      };
    },
    methods: {
      register() {
        // Kiểm tra xem mật khẩu và xác nhận mật khẩu có khớp không
        if (this.user.password !== this.user.confirmPassword) {
          alert('Mật khẩu và xác nhận mật khẩu không khớp.');
          return;
        }
  
        // Tạo một đối tượng người dùng mới, loại bỏ confirmPassword
        const newUser = {
          name: this.user.name,
          email: this.user.email,
          password: this.user.password
        };
  
        // Hiển thị đối tượng người dùng trong console
        console.log('Người dùng mới:', newUser);
  
        // Reset form sau khi đăng ký thành công
        this.resetForm();
      },
      resetForm() {
        this.user.name = '';
        this.user.email = '';
        this.user.password = '';
        this.user.confirmPassword = '';
      }
    }
  };
</script>
  
<style scoped>
  .exercise08 {
    max-width: 500px;
    margin: 0 auto;
    padding: 25px;
    font-family: Arial, sans-serif;
    background-color: #ffffff;
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  }
  
  h2 {
    text-align: center;
    margin-bottom: 25px;
    color: #333;
  }
  
  form {
    display: flex;
    flex-direction: column;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: #555;
  }
  
  input {
    width: 100%;
    padding: 10px 14px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
  }
  
  input:focus {
    border-color: #66afe9;
    outline: none;
    box-shadow: 0 0 5px rgba(102, 175, 233, 0.6);
  }
  
  .btn {
    padding: 12px 20px;
    background-color: #28a745;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease;
  }
  
  .btn:hover {
    background-color: #218838;
  }
</style>
  