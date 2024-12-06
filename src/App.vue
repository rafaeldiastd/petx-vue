<script setup>
import axios from 'axios';
import { ref } from 'vue';

const animals = ref('')

const dados = {
  "email": "rafa@gmail.com",
  "password": "123456"
}

const getAnimals = async () => {

  try {
    const response = await axios.post('https://petx-v4.onrender.com/api/auth/login', dados)
    animals.value = response.data

  } catch (error) {
    console.error(error)
  }
}

getAnimals()

</script>

<template>

  <div v-if="animals">{{ animals }}</div>
  <div v-else>Carregando.</div>

</template>

<style lang="postcss" scoped></style>