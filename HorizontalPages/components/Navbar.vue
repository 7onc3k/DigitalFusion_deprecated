<template>
    <div>
      <button @click="moveTo('home')">Home</button>
      <button @click="moveTo('about')">About</button>
      <button @click="moveTo('projects')">Projects</button>
      <button @click="moveTo('contact')">Contact Us</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      moveTo(page) {
        const index = ['home', 'about', 'projects', 'contact'].indexOf(page);
        const container = document.querySelector('.pages-container');
        container.style.transform = `translateX(-${index * 100}vw)`;
      }
    }
  }
  </script>
  