<template>
    <div class="flex flex-col min-h-screen bg-gray-100">
      <NavigationBar />
      <main class="flex-grow p-4 md:p-6">
        <slot />
      </main>
      <Footer />
    </div>
</template>

<script>
import NavigationBar from '~/components/NavigationBar.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    NavigationBar,
    Footer
  }
}
</script>

<style scoped>
/* Pokud chcete přidat nějaké vlastní styly, můžete je umístit sem. */
</style>
