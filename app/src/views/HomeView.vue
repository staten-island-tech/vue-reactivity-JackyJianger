<script setup>
import AnimalCard from '../components/AnimalCard.vue'
const animals = [
{
    name: "Walrus", image: "/Walrus.webp"
},
{
    name:"Mark Fridlan", image:"/capy.webp"
}];
</script>

<template>
  <main>
    <AnimalCard v-for="animal in animals" :key ="animal.name" :animals="animal" />
  </main>
</template>
