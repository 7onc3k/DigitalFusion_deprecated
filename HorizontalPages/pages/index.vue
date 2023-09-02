<!-- pages/index.vue -->

<template>
    <div class="page-content">
      <Home />
      <About />
      <Projects />
      <Contact />
    </div>
  </template>
  
  <script>
  import Home from '~/pages/home.vue'
  import About from '~/pages/about.vue'
  import Projects from '~/pages/projects.vue'
  import Contact from '~/pages/contact.vue'
  
  export default {
    components: {
      Home,
      About,
      Projects,
      Contact
    }
  }
  </script>
  
  <style scoped>
  .page-content {
    display: flex;
    width: 100%;
  }
  </style>
  