<template>
    <div>
    <img :src="animal.image" alt=""/>
    </div>
</template>

<script setup>
defineProps({
    animal: Object, 
})
</script>

<style  scoped>

</style>