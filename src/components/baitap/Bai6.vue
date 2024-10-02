<template>
    <div class="exercise06">
      <h2>Chọn Sở Thích</h2>
      <label>
        <input 
          type="checkbox" 
          value="Đọc sách" 
          v-model="hobbies" 
        />
        Đọc sách
      </label>
      <label>
        <input 
          type="checkbox" 
          value="Nghe nhạc" 
          v-model="hobbies" 
        />
        Nghe nhạc
      </label>
      <label>
        <input 
          type="checkbox" 
          value="Chơi thể thao" 
          v-model="hobbies" 
        />
        Chơi thể thao
      </label>
      <label>
        <input 
          type="checkbox" 
          value="Đi du lịch" 
          v-model="hobbies" 
        />
        Đi du lịch
      </label>
  
      <h3>Sở thích đã chọn:</h3>
      <ul>
        <li v-for="hobby in hobbies" :key="hobby">{{ hobby }}</li>
      </ul>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise06',
    data() {
      return {
        hobbies: [] // Mảng chứa các sở thích đã chọn
      };
    }
  };
</script>
  
<style scoped>
  .exercise06 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
  }
  
  h2, h3 {
    text-align: center;
  }
  
  label {
    display: block;
    margin: 10px 0;
    font-weight: bold;
  }
  
  ul {
    margin-top: 20px;
    list-style-type: none;
    padding: 0;
    text-align: center;
  }
  
  li {
    margin: 5px 0;
    font-size: 1.1em;
    color: #333;
  }
</style>
  