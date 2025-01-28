<template>
    <div>
        <form name="login-form" action="click" @submit.prevent="login(user)">
        <label for="username">Enter Username</label>
        <input type="text" v-model="user.username"/>
        <label for="password">Enter Password</label>
        <input type="password" v-model="user.password"/>
        <button type="submit">Submit</button>
        </form>
    </div>
</template>

<script setup>
import { reactive } from 'vue';
const user = reactive({username:'', password: ''})
function login(user){
    console.log(user)
}
</script>

<style scoped>

</style>