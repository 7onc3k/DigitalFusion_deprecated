<template>
    <div class="navbar">
      <div class="links" :style="{ transform: `translateX(${moveAmount}%)` }">
        <nuxt-link v-for="link in links" :key="link.name" :to="link.path" :class="{ active: isActive(link.path) }">{{ link.name }}</nuxt-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        links: [
          { name: 'Home', path: '/' },
          { name: 'About', path: '/about' },
          { name: 'Projects', path: '/projects' },
          { name: 'Contact', path: '/contact' }
        ]
      }
    },
    computed: {
      moveAmount() {
        const index = this.links.findIndex(link => this.isActive(link.path));
        return -index * 25 + 37.5;  // Posuneme o 37.5% (polovina šířky odkazu a gapu mezi odkazy) ke středu
      }
    },
    methods: {
      isActive(path) {
        return this.$route.path === path;
      }
    }
  }
  </script>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: center;
    overflow: hidden;
    width: 100%;
    position: relative;
  }
  
  .links {
    display: flex;
    gap: 20px;
    transition: transform 0.3s ease;
  }
  
  nuxt-link {
    width: 100px;
    text-align: center;
  }
  
  .active {
    font-weight: bold;
  }
  </style>
  