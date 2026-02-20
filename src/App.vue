<template>
  <div class="d-flex flex-column min-vh-100">
    <Navbar />
    <main class="flex-fill" style="padding-top: 0;">
      <RouterView />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
</script>

<style>
*, *::before, *::after { box-sizing: border-box; }
body { margin: 0; padding: 0; background: #fdf6ec; }
</style>