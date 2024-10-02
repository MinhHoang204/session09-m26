<template>
    <div class="exercise01">
      <h2>Nhập địa chỉ Email</h2>
      <input
        type="email"
        v-model="email"
        placeholder="Nhập email của bạn"
      />
      <p>Giá trị nhập vào: {{ email }}</p>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise01',
    data() {
      return {
        email: ''
      };
    }
  };
</script>
  
<style scoped>
  .exercise01 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
  }
  
  input {
    width: 100%;
    padding: 8px;
    margin-top: 10px;
    box-sizing: border-box;
  }
  
  p {
    margin-top: 15px;
    font-weight: bold;
  }
</style>
  