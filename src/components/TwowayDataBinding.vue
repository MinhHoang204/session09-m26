<template>
  <form @submit.prevent="handleSubmit">
    <h2>userName: {{ userInfo.userName }}</h2>
    <h2>dateOfBirth: {{ userInfo.dateOfBirth }}</h2>
    <h2>gender: {{ userInfo.gender }}</h2>
    <h2>Hobbies: {{ userInfo.hobbies }}</h2>

    <h3>Them moi nguoi dung</h3>
    <div>
        Ho va ten:<input v-model="userInfo.userName" type="text" placeholder="Nhap ten"/>
    </div>
    <div>Ngay sinh:<input v-model="userInfo.dateOfBirth" type="date"/></div>
    <div>Gioi tinh:</div>
    <div>
       Nam 
       <input name="gender" v-model="gender" type="radio" value="0"/> 
       Nu 
        <input name="gender" v-model="gender" type="radio" value="1"/> 
       Khac
        <input name="gender" v-model="gender" type="radio" value="2"/>
    </div>
    <div>So thich</div>
    <div>
       Choi game
       code <input value="code" v-model="hobbies" type="checkbox"/>
       Boi loi <input value="swim" v-model="hobbies" type="checkbox"/>
       Bong chuyen <input value="volleyball" v-model="hobbies" type="checkbox"/>
       Bong da <input value="soccer" v-model="hobbies" type="checkbox"/>
    </div>
    <button>Them</button>
  </form>
</template>

<script setup>
import { reactive, ref } from 'vue';

const userName = ref("");
const dateOfBirth = ref("");
const gender = ref("0");
const hobbies = ref([]);

const userInfo = reactive({
    userName: "",
    dateOfBirth: "",
    gender: "0",
    hobbies: [],
});

const handleSubmit = () => {
    // Ngan chan su kien load lai trang
    // e.prevenDefault();
    const user = {
        userName: userName.value,
        dateOfBirth: dateOfBirth.value,
        gender: gender.value,
        hobbies: hobbies.value,
    }
    console.log("Submited", user);
}
</script>

<style>

</style>