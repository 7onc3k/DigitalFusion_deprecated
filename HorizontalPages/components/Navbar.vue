<template>
  <div class="navbar-container">
    <button 
      v-for="link in links" 
      :key="link.name" 
      @click="moveTo(link.name)" 
      :class="{ active: currentLink === link.name }"
    >
      {{ link.label }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        { name: 'home', label: 'Home' },
        { name: 'about', label: 'About' },
        { name: 'projects', label: 'Projects' },
        { name: 'contact', label: 'Contact Us' }
      ],
      currentLink: 'home'
    }
  },
  methods: {
    moveTo(page) {
      const index = this.links.findIndex(link => link.name === page);
      this.currentLink = page;

      // Posunutí kontejneru stránek
      const container = document.querySelector('.pages-container');
      container.style.transform = `translateX(-${index * 100}vw)`;

      // Posunutí navbar kontejneru pro vycentrování aktuálního odkazu
      const offset = 50 - (index * 25 + 12.5); // 25% pro každý odkaz, 12.5% je polovina jednoho odkazu
      this.$el.style.transform = `translateX(${offset}vw)`;
    }
  }
}
</script>

<style scoped>
.navbar-container {
  display: flex;
  transition: all 0.3s ease;
}

button {
  flex: 1;
  width: 25vw; /* Každé tlačítko má šířku 25% celkové šířky okna prohlížeče */
  font-weight: normal;
}

button.active {
  font-weight: bold;
}
</style>
