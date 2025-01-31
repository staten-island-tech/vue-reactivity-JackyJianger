<template>
    <div class="card">
      <h3>{{ saladtoppings.name }}</h3>
      <img :src="saladtoppings.image" alt="Image of {{ saladtoppings.name }}" class="card-image" />
    </div>
  </template>
  
  <script setup>
  defineProps({
    saladtoppings: Object,
  })
  </script>
  
  <style scoped>
  .card {
    border: 1px solid #ddd;
    padding: 16px;
    width: 200px;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
    margin: 10px;
  }
  
  .card-image {
    width: 100%;
    height: auto;
    border-radius: 4px;
  }
  </style>