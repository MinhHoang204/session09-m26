<template>
    <div class="exercise05">
      <h2>Chọn Giới Tính</h2>
      <label>
        <input 
          type="radio" 
          value="Nam" 
          v-model="gender" 
        />
        Nam
      </label>
      <label>
        <input 
          type="radio" 
          value="Nữ" 
          v-model="gender" 
        />
        Nữ
      </label>
      <label>
        <input 
          type="radio" 
          value="Khác" 
          v-model="gender" 
        />
        Khác
      </label>
  
      <p>Giới tính được chọn: {{ gender }}</p>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise05',
    data() {
      return {
        gender: '' // Biến lưu trữ giới tính được chọn
      };
    }
  };
</script>
  
<style scoped>
  .exercise05 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
  }
  
  h2 {
    text-align: center;
  }
  
  label {
    display: block;
    margin: 10px 0;
    font-weight: bold;
  }
  
  p {
    margin-top: 20px;
    font-size: 1.1em;
    color: #333;
    text-align: center;
  }
</style>
  