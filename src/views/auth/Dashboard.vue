<script setup lang="ts">
import {ref} from 'vue';
import axiosInstance from '@/lib/axios';

const user = ref({
  name: "",
  email: "",
});


const getuser = async () => {
  try {
    const response = await axiosInstance.get('/user');
    console.log("get user..",response);
    
    user.value = response.data;
  } catch (error) {
    console.error(error);
  }
};

const logout = async () => {
  try {
    await axiosInstance.post('/logout');
    user.value ={
      name: "",
      email: "",

    };
  } catch (error) {
    console.error(error);
  }
};
getuser();
</script>

<template>
    <h1 class="text-3xl text-slate-200">Dashboard</h1>
    <div>
      <div>
        <p class="text-lg text-slate-200">Welcome black, {{ user?.name }}</p>
        <p class="text-lg text-slate-200">{{ user?.email }}</p>
      </div>
      <button @click="logout" class="btn btn-primary">Logout</button>
    </div>
</template>