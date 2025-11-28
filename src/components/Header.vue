<template>
  <header class="fixed top-0 left-0 right-0 z-50 bg-dark/80 backdrop-blur-md border-b border-primary/20">
    <nav class="container mx-auto px-4 py-4">
      <div class="flex items-center justify-between">
        <!-- Logo -->
        <div class="text-2xl font-bold text-primary">
          Freedom for the Monkey
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="#home" class="nav-link">Home</a>
          <a href="#tokenomics" class="nav-link">Tokenomics</a>
          <a href="#roadmap" class="nav-link">Roadmap</a>
          <a href="#community" class="nav-link">Community</a>
          <a href="#airdrop" class="nav-link">Airdrop</a>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden text-white focus:outline-none"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              v-if="!mobileMenuOpen"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path
              v-else
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Navigation -->
      <div
        v-if="mobileMenuOpen"
        class="md:hidden mt-4 pb-4 space-y-3"
      >
        <a href="#home" class="block nav-link" @click="mobileMenuOpen = false">Home</a>
        <a href="#tokenomics" class="block nav-link" @click="mobileMenuOpen = false">Tokenomics</a>
        <a href="#roadmap" class="block nav-link" @click="mobileMenuOpen = false">Roadmap</a>
        <a href="#community" class="block nav-link" @click="mobileMenuOpen = false">Community</a>
        <a href="#airdrop" class="block nav-link" @click="mobileMenuOpen = false">Airdrop</a>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)
</script>

<style scoped>
.nav-link {
  @apply text-white hover:text-primary transition-colors duration-300 font-medium;
}
</style>
