<template>
  <main>
    <div class="cards-container">
      <AnimalCard v-for="saladtopping in saladtoppings" :key="saladtopping.name" :saladtoppings="saladtopping" />
    </div>
  </main>
</template>

<script setup>
import AnimalCard from '../components/AnimalCard.vue'

const saladtoppings = [
  { name: "Olive", image: "/path-to-olive-image.jpg" },
  { name: "Tomato", image: "/capy.webp" },
  { name:"Ranch", image:"/ranch.jpg"},
  { name:"Chipotle Ranch", image:"/chipotle-ranch.jpg"}, 
  { name:"", image:""}

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