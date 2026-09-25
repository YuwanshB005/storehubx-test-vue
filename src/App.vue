<script setup>
import Navbar from './components/Navbar.vue'
</script>

<template>
  <Navbar />
  <main class="page">
    <p>Scroll and resize to see the navbar's mobile menu toggle.</p>
  </main>
</template>

<style scoped>
.page {
  min-height: 60vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #6b7280;
  font-size: 0.9rem;
}
</style>
