<template>
  <div class="navbar-container">
    <button v-for="link in links" :key="link.name" @click="moveTo(link.name)"
      :class="{ active: currentLink === link.name }">
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
      this.updatePosition(index);
    },
    updatePosition(index) {
  // Posunutí kontejneru stránek
  const container = document.querySelector('.pages-container');
  container.style.transform = `translateX(-${index * 100}vw)`;

  // Posunutí navbar kontejneru pro vycentrování aktuálního odkazu
  const offset = - index * 6.25 + 9.375;  // Aktualizujeme výpočet pro novou šířku tlačítek
  this.$el.style.transform = `translateX(${offset}vw)`;
}



  },
  mounted() {
    // Inicializujte výchozí stav pro navigační lištu a kontejner stránky
    const defaultIndex = this.links.findIndex(link => link.name === this.currentLink);
    this.updatePosition(defaultIndex);
  }
}
</script>

<style scoped>
.navbar-container {
  display: flex;
  justify-content: center;
  width: 25vw;
  margin: 0 auto;
  transition: all 0.3s ease;
  text-transform: uppercase;
  
    /* Všechny texty v capslocku */
  
}

button {
  flex: 1;
  width: 6.25vw;
  font-weight: normal;
  opacity: 0.6;  /* Neaktivní odkazy průhledné */
  transform: scale(0.9);  /* Neaktivní odkazy menší */
  transition: all 0.3s ease;
  min-width: 70px;
  
  
}

button.active {
  font-weight: bold;
  opacity: 1;  /* Aktivní odkaz plně viditelný */
  transform: scale(1);
  
  
  /* Aktivní odkaz normální velikost */
}


</style>
