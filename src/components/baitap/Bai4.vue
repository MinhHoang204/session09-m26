<template>
    <div class="exercise04">
      <h2>Kiểm Tra Tiến Độ Hoàn Thành Công Việc</h2>
      <input
        type="range"
        v-model="progress"
        min="0"
        max="100"
        @input="updateProgress"
      />
      <p>Tiến độ hiện tại: {{ progress }}%</p>
      <div class="progress-bar">
        <div class="progress" :style="{ width: progress + '%' }"></div>
      </div>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise04',
    data() {
      return {
        progress: 0 // Giá trị ban đầu của tiến độ là 0
      };
    },
    methods: {
      updateProgress(event) {
        this.progress = event.target.value;
      }
    }
  };
</script>
  
<style scoped>
  .exercise04 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
    font-family: Arial, sans-serif;
  }
  
  input[type="range"] {
    width: 100%;
    margin-top: 10px;
  }
  
  p {
    margin-top: 15px;
    font-weight: bold;
    color: #333;
  }
  
  .progress-bar {
    width: 100%;
    height: 30px;
    background-color: #e0e0e0;
    border-radius: 5px;
    margin-top: 20px;
    overflow: hidden;
  }
  
  .progress {
    height: 100%;
    background-color: #4caf50;
    border-radius: 5px;
    transition: width 0.3s ease;
  }
</style>
  