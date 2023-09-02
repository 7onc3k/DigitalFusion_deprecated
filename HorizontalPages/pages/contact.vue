--- Path: d:\Projekty\DigitalFusion\DigitalFusion\pages\contact\index.vue ---
<template>
    <div class="container max-w-screen-xl mx-auto p-4 md:p-6">
      <h1 class="text-4xl font-bold mb-8">Kontaktujte nás</h1>
      <img src="/path-to-clipart-contact.png" alt="Kontakt obrázek" class="mb-8 w-full h-48 md:h-auto object-cover">
      <form @submit.prevent="submitForm" class="bg-white p-4 md:p-8 rounded-lg shadow-md">
        <div class="mb-4">
          <label for="name" class="block mb-2">Jméno:</label>
          <input type="text" id="name" v-model="formData.name" class="p-2 border rounded w-full">
        </div>
        <div class="mb-4">
          <label for="email" class="block mb-2">Email:</label>
          <input type="email" id="email" v-model="formData.email" class="p-2 border rounded w-full">
        </div>
        <div class="mb-4">
          <label for="message" class="block mb-2">Zpráva:</label>
          <textarea id="message" v-model="formData.message" class="p-2 border rounded w-full h-32"></textarea>
        </div>
        <button type="submit" class="bg-gradient-to-r from-blue-500 to-indigo-600 text-white w-full md:w-auto px-4 py-2 mt-4 rounded shadow hover:shadow-md transition">Odeslat</button>

      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const formData = ref({
    name: '',
    email: '',
    message: ''
  })
  
  const submitForm = () => {
    // Odešlete formulář, například pomocí axios nebo jiného způsobu
    alert('Formulář odeslán!'); 
  }
  </script>
  

