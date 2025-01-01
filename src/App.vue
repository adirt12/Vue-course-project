<script setup>
  import { ref } from 'vue';

  const name = ref('adi levi');
  const status = ref('active');
  const tasks = ref(['Task One','Task Two','Task Three']);
  
  const toggleStatus = () => {
    if (status.value === 'active'){
      status.value = 'pending'
    }
    else if(status.value === 'pending') {
      status.value = 'inactive'
    }
    else{
      status.value = 'active'
    }
  }
</script>

<template>
  <h1>{{name}}</h1>
  <p>User is {{ status }}</p>
  <h2>Tasks:</h2>
  <ul>
    <li v-for="task in tasks">{{ task }}</li>
  </ul>
  <button @click="toggleStatus">Change status</button>
</template>

