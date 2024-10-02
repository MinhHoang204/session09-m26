<template>
    <div class="exercise03">
      <h2>Nhập Ngày Sinh</h2>
      <input
        type="date"
        v-model="birthDate"
        placeholder="Chọn ngày sinh của bạn"
      />
      <p>Ngày sinh đã nhập: {{ formattedBirthDate }}</p>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise03',
    data() {
      return {
        birthDate: ''
      };
    },
    computed: {
      formattedBirthDate() {
        if (this.birthDate) {
          const options = { year: 'numeric', month: 'long', day: 'numeric' };
          return new Date(this.birthDate).toLocaleDateString('vi-VN', options);
        }
        return 'Chưa chọn ngày';
      }
    }
  };
</script>
  
<style scoped>
  .exercise03 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
    font-family: Arial, sans-serif;
  }
  
  input[type="date"] {
    width: 100%;
    padding: 8px;
    margin-top: 10px;
    box-sizing: border-box;
    font-size: 16px;
  }
  
  p {
    margin-top: 15px;
    font-weight: bold;
    color: #333;
  }
</style>
  