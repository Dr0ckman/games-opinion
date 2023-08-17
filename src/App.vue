<template>
  <Navbar />
  <div class="content-wrap">
    <font-awesome-icon icon="fa-solid fa-user-secret" />
    <router-view />
  </div>
  <Footer />
</template>

<style>
html {
  position: relative;
}

.content-wrap {
  min-height: 100vh;
  padding-bottom: 3rem;
}
</style>

<script>
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Navbar,
    Footer
  }
}
</script>