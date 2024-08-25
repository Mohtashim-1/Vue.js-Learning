<template>
<div v-if="data">
  <!-- <ul>
    <li v-for="item in data">
      {{ item.name }}
    </li>
  </ul> -->
  <Item v-for="item in data" :name="item.name"></Item>
</div>

</template>

<script setup>

import { ref, onMounted } from 'vue';
import Item from './Item.vue'
const data = ref(null)
onMounted(()=>{
  fetch('/api/resource/Employee', {
    method: 'GET',
    headers:{
      'Authorization':'Token 014f885e44c7fd9:6cc066db28b9345',
      'Content-Type':'application/json'
    }
  })
  .then(response => response.json())
  .then(message =>{
    data.value = message.data
  })
  .catch(error=>{
    console.log('Error', error)
  })
})

</script>