<template>
  <main>
    <div class="image-display">
      <img v-if="imageVisible" :src="selectedImage" alt="Selected Topping" />
    </div>
    <btn class="cards-container">
      <button 
        v-for="saladtopping in saladtoppings" 
        :key="saladtopping.name" 
        @click="addImage(saladtopping)" 
        class="topping-button">
        <AnimalCard :saladtoppings="saladtopping" :style="cardStyle" />
      </button>
    </btn>
  </main>
</template>

<script setup>
import { ref } from 'vue';
import AnimalCard from '../components/AnimalCard.vue'


const saladtoppings = [
  { name: "Olive", image: "/images/olives.png" },
  { name: "Tomato", image: "/images/tomato.webp" },
  { name:"Ranch", image:"/ranch.jpg"},
  { name:"Chipotle Ranch", image:"/chipotle-ranch.jpg"}, 
  { name:"Nuts", image:""},
  { name:"Seeds", image:""},
  { name:"Beans", image:""},
  { name:"Fruit", image:""},
  { name:"Corn", image:""},
  { name:"Guacamole", image:""}
];
const imageVisible = ref(false);
const selectedImage = ref('');
const addImage = (saladtopping) => {
  selectedImage.value = saladtopping.image;
  imageVisible.value = true;
};
</script>



<style scoped>

.cards-container {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}
.image-display {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  width: 300px; 
  height: auto; 
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.image-display img {
  width: 100%;
  height: auto; 
}
.topping-button {
  background: none;
  border: none;
  cursor: pointer;
}
</style>