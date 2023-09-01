<template>
    <nav class="p-4 bg-transparent">
      <ul class="flex justify-between items-center container mx-auto">
        <li><a href="/" class="text-white">Logo</a></li>
        <div class="bg-white h-14 p-2 rounded-full shadow-md flex space-x-4 items-center">
          <li><a href="/" :class="isActive('/')"><i class="fas fa-home text-black px-4 py-2 rounded-full"></i></a></li>
          <li><a href="/about" :class="isActive('/about')"><i class="fas fa-user text-black px-4 py-2 rounded-full"></i></a></li>
          <li><a href="/projects" :class="isActive('/projects')"><i class="fas fa-crane text-black px-4 py-2 rounded-full"></i></a></li>
          <li><a href="/contact" :class="isActive('/contact')"><i class="fas fa-envelope text-black px-4 py-2 rounded-full"></i></a></li>
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
        return this.currentPath === path ? 'bg-blue-500' : '';
      }
    }
  }
</script>
