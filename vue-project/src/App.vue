<script setup>
import { ref } from "vue";
    const name= ref("Salsa");
    const status= ref("active");
    const tasks= ref(["task one", "task two", "task three"]);
    const link= ref("https://google.com");

  const toggleStatus =()=>{
    if(status.value == "active"){
      status.value = "pending"
    }
    else if (status.value == "pending"){
      status.value = "inactive"
    }
    else {
      status.value = "active"
    }
  }
 
</script>


<template>
  <h1>{{name}}</h1>
  <p v-if="status == 'active'">User is active</p>
  <p v-else-if="status == 'pending'">User is pending</p>
  <p v-else> User is inactive</p>

  <h3>Task</h3>
  <ul>
    <li v-for="task in tasks" :key="task">
      {{ task }}
    </li>
  </ul>
  <a :href="link">Click me</a>

  <button @click="toggleStatus">change status</button>
</template>


