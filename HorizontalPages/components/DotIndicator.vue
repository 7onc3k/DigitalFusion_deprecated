<template>
  <div class="dots-container">
    <div
      v-for="link in links"
      :key="link.name"
      class="dot"
      :class="{ active: currentLink === link.name }"
      @click="moveTo(link.name)"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    currentLink: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      links: [
        { name: 'home', label: 'Home' },
        { name: 'about', label: 'About' },
        { name: 'projects', label: 'Projects' },
        { name: 'contact', label: 'Contact Us' }
      ]
    };
  },
  methods: {
    moveTo(page) {
      this.$emit('changePage', page);
    }
  }
};
</script>

<style scoped>
.dots-container {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
}

.dot {
  width: 10px;
  height: 10px;
  background-color: rgba(0, 0, 0, 0.2);
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s ease;
}

.dot.active {
  background-color: black;
}



</style>
