<template>
    <div class="exercise02">
      <h2>Chọn Màu Sắc</h2>
      <input
        type="color"
        v-model="selectedColor"
        @input="updateColor"
      />
      <p>Mã màu đã chọn: {{ selectedColor }}</p>
      <div
        class="color-display"
        :style="{ backgroundColor: selectedColor }"
      ></div>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise02',
    data() {
      return {
        selectedColor: '#000000' // Giá trị mặc định là màu đen
      };
    },
    methods: {
      updateColor(event) {
        this.selectedColor = event.target.value;
      }
    }
  };
</script>
  
<style scoped>
  .exercise02 {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }
  
  input[type="color"] {
    width: 100%;
    height: 50px;
    border: none;
    padding: 0;
    margin-top: 10px;
    cursor: pointer;
  }
  
  p {
    margin-top: 15px;
    font-weight: bold;
  }
  
  .color-display {
    width: 100%;
    height: 100px;
    margin-top: 10px;
    border: 1px solid #ccc;
  }
</style>
  