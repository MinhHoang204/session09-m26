<template>
    <div class="exercise07">
      <h2>Thêm Sản Phẩm Mới</h2>
      <form @submit.prevent="addProduct">
        <div class="form-group">
          <label for="productCode">Mã sản phẩm:</label>
          <input
            type="text"
            id="productCode"
            v-model="product.productCode"
            required
            placeholder="Nhập mã sản phẩm"
          />
        </div>
  
        <div class="form-group">
          <label for="productName">Tên sản phẩm:</label>
          <input
            type="text"
            id="productName"
            v-model="product.productName"
            required
            placeholder="Nhập tên sản phẩm"
          />
        </div>
  
        <div class="form-group">
          <label for="price">Giá:</label>
          <input
            type="number"
            id="price"
            v-model.number="product.price"
            required
            min="0"
            placeholder="Nhập giá sản phẩm"
          />
        </div>
  
        <div class="form-group">
          <label for="quantity">Số lượng:</label>
          <input
            type="number"
            id="quantity"
            v-model.number="product.quantity"
            required
            min="0"
            placeholder="Nhập số lượng sản phẩm"
          />
        </div>
  
        <button type="submit" class="btn">Thêm mới</button>
      </form>
    </div>
</template>
  
<script>
  export default {
    name: 'Exercise07',
    data() {
      return {
        product: {
          productCode: '',
          productName: '',
          price: null,
          quantity: null
        }
      };
    },
    methods: {
      addProduct() {
        // Kiểm tra tính hợp lệ của dữ liệu (nếu cần)
        if (
          this.product.productCode.trim() === '' ||
          this.product.productName.trim() === '' ||
          this.product.price === null ||
          this.product.quantity === null
        ) {
          alert('Vui lòng điền đầy đủ thông tin sản phẩm.');
          return;
        }
  
        // Tạo một đối tượng sản phẩm mới
        const newProduct = { ...this.product };
  
        // Hiển thị đối tượng sản phẩm trong console
        console.log('Sản phẩm mới:', newProduct);
  
        // Reset form sau khi thêm sản phẩm
        this.resetForm();
      },
      resetForm() {
        this.product.productCode = '';
        this.product.productName = '';
        this.product.price = null;
        this.product.quantity = null;
      }
    }
  };
</script>
  
<style scoped>
  .exercise07 {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
    background-color: #fafafa;
    border: 1px solid #ddd;
    border-radius: 8px;
  }
  
  h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #333;
  }
  
  form {
    display: flex;
    flex-direction: column;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
    color: #555;
  }
  
  input {
    width: 100%;
    padding: 8px 12px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  input:focus {
    border-color: #66afe9;
    outline: none;
  }
  
  .btn {
    padding: 10px 15px;
    background-color: #28a745;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
  }
  
  .btn:hover {
    background-color: #218838;
  }
</style>
  