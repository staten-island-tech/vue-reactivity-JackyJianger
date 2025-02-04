<template>
  <main>
    <btn class="cards-container">
      <AnimalCard v-for="saladtopping in saladtoppings" :key="saladtopping.name" :saladtoppings="saladtopping"  :style="cardStyle"/>
    </btn>
  </main>
</template>

<script setup>
import AnimalCard from '../components/AnimalCard.vue'


const saladtoppings = [
  { name: "Olive", image: "/path-to-olive-image.jpg" },
  { name: "Tomato", image: "/capy.webp" },
  { name:"Ranch", image:"/ranch.jpg"},
  { name:"Chipotle Ranch", image:"/chipotle-ranch.jpg"}, 
  { name:"Nuts", image:""},
  { name:"Seeds", image:""},
  { name:"Beans", image:""},
  { name:"Fruit", image:""},
  { name:"Corn", image:""},
  { name:"Guacamole", image:""}
];
</script>



<style scoped>
.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}
</style>