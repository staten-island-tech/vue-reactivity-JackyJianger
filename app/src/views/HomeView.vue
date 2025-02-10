<template>
  <main>
    <div class="image-display">
      <div v-for="(image, index) in selectedImages" :key="index" class="stacked-image-container">
        <img :src="image" alt="Selected Topping" class="stacked-image" />
      </div>
    </div>
    <div class="cards-container">
      <button 
        v-for="saladtopping in saladtoppings" 
        :key="saladtopping.name" 
        @click="addImage(saladtopping)" 
        class="topping-button">
        <AnimalCard :saladtoppings="saladtopping" />
      </button>
    </div>
  </main>
</template>

<script setup>
import { reactive, ref } from 'vue';
import AnimalCard from '../components/AnimalCard.vue'


const saladtoppings = [
  { name: "Olive", image: "/images/olives.png" },
  { name: "Tomato", image: "/images/tomato.webp" },
  { name:"Ranch", image:"/image/ranch.jpg"},
  { name:"Chipotle Ranch", image:"/chipotle-ranch.jpg"}, 
  { name:"Nuts", image:"/images/nuts.webp"},
  { name:"Seeds", image:"/images/seeds.webp"},
  { name:"Beans", image:"/images/beans.png"},
  { name:"Fruit", image:"/images/fruit.png"},
  { name:"Corn", image:"/images/corn.png"},
];
const selectedImages = reactive([]);

const addImage = (saladtopping) => {
  if (!selectedImages.includes(saladtopping.image)) {
    selectedImages.push(saladtopping.image);
  }
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
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative; 
  padding: 10px;
  gap: 5px;
}
.stacked-image-container {
  position: absolute;
  width: 100px;
  height: 100px;
}

.stacked-image {
  position: absolute;
  width: 100px; 
  height: 100px;
  object-fit: contain;
  z-index: 10;
}
.image-display img {
  width: 100%;
  height: auto; 
  object-fit: contain;  
}
.topping-button {
  background: none;
  border: none;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cards-container img {
  width: 50px;
  height: 50px; 
  object-fit: contain;
}
</style>