<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="columns is-mobile">
        <div class="column main-page-contents">
          <Nuxt />
        </div>
      </div> <!-- .columns -->
    </div> <!-- .container -->
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>
