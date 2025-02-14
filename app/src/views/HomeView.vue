<template>
  <main>
    <img src="/images/plate.png" alt="hi" class="plates">
    <button class="clearButton" @click="clear">Clear</button>
    <div v-for="(image, index) in selectedImages" :key="index" class="stacked-image-container">
        <img :src="image" alt="Selected Topping" class="stacked-image" />
      </div>
    <div class="image-display">    </div>
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
  { name:"Nuts", image:"/images/nuts.webp"},
  { name:"Seeds", image:"/images/seeds.webp"},
  { name:"Beans", image:"/images/beans.png"},
  { name:"Fruit", image:"/images/fruit.png"},
  { name:"Corn", image:"/images/corn.png"},
];
const selectedImages = reactive([]);

const addImage = (saladtopping) => {
    selectedImages.push(saladtopping.image);
};
function clear() {
  selectedImages.splice(0, selectedImages.length);
}

</script>



<style scoped>
.clearButton{
  position:absolute;
  left: 21.50%;
  top:72%;
}
.plates{
  position:absolute;
  width:300px;
  height:auto;
  left:15%;
  top:40%;
}
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
  top: 45%; 
  left: 17.5%;
  position: absolute;
  width: 200px;
  height: auto;
}

.stacked-image {
  position: absolute;
  width: 200px; 
  height: auto;
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