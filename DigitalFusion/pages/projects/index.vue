<template>
    <div class="container max-w-screen-xl mx-auto p-4 md:p-6">
      <h1 class="text-4xl font-bold mb-8">Naše projekty</h1>
      <div class="grid grid-cols-1 gap-4 md:grid-cols-3 md:gap-8">
        <div v-for="project in projects" :key="project.name" class="card p-4 border rounded-lg shadow-md hover:shadow-lg transition">
          <img :src="project.image" :alt="project.name" class="mb-4 w-full h-48 object-cover">
          <h2 class="text-2xl font-bold">{{ project.name }}</h2>
          <p class="mt-2">{{ project.description }}</p>
        </div>
      </div>
    </div>
</template>

  <script setup>
  import { ref } from 'vue'
  
  const projects = ref([
    { name: 'Projekt 1', description: 'Popis projektu 1', image: '/path-to-project1-image.png' },
    { name: 'Projekt 2', description: 'Popis projektu 2', image: '/path-to-project2-image.png' },
    // ... další projekty
  ])
  </script>
  