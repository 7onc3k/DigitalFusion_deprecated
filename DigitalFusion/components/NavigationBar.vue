<template>
    <nav class="p-4 bg-transparent">
      <ul class="flex justify-between items-center container mx-auto">
        <li><a href="/" class="text-white">Logo</a></li>
        <div class="bg-white p-4 rounded-lg shadow-md flex space-x-4 items-center">
          <li><a href="/" :class="isActive('/')" class="text-black px-4 py-2 rounded-md">Domů</a></li>
          <li><a href="/about" :class="isActive('/about')" class="text-black px-4 py-2 rounded-md">O nás</a></li>
          <li><a href="/projects" :class="isActive('/projects')" class="text-black px-4 py-2 rounded-md">Projekty</a></li>
          <li><a href="/contact" :class="isActive('/contact')" class="text-black px-4 py-2 rounded-md">Kontaktujte nás</a></li>
        </div>
        <button @click="showMenu = !showMenu" class="md:hidden">
          ☰
        </button>
      </ul>
    </nav>
  </template>
  
  
  <script>
  export default {
    data() {
      return {
        showMenu: false
      }
    },
    computed: {
      currentPath() {
        return this.$route.path;
      }
    },
    methods: {
      isActive(path) {
        return this.currentPath === path ? 'bg-blue-500 shadow-md' : '';
      }
    }
  }
  </script>
  
