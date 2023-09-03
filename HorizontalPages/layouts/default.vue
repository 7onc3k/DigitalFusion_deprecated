<template>
  <div>
    
    <div class="pages-container">
      <slot/>
    </div>
    <Navbar @updateCurrentLink="updateCurrentLink" />
    <DotIndicator :currentLink="currentLink" />
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import DotIndicator from '~/components/DotIndicator.vue'

export default {
  components: {
    Navbar,
    DotIndicator
  },
  data() {
    return {
      currentLink: 'home'
    }
  },
  methods: {
    updateCurrentLink(newLink) {
      this.currentLink = newLink;
    }
  }
}
</script>

<style>
.pages-container {
  display: flex;
  width: 400%; /* Protože máme 4 stránky */
  transition: all 0.3s ease; /* Přidá animaci při posunu */
}




</style>
