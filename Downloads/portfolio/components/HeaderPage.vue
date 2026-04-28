<template>
  <header class="bg-gray-900 text-white shadow-md fixed w-full z-50">
    <div class="max-w-7xl mx-auto flex items-center justify-between p-4">
      <h1 class="text-2xl font-bold">Kartik Shah</h1>

      <nav>
        <!-- Desktop Menu -->
        <ul class="hidden md:flex gap-6">
          <li><NuxtLink to="/" class="hover:text-blue-400 font-bold text-xl">Home</NuxtLink></li>
          <li><NuxtLink to="/Abouts" class="hover:text-blue-400 font-bold text-xl">About</NuxtLink></li>
          <li><NuxtLink to="/Projects" class="hover:text-blue-400 font-bold text-xl">Projects</NuxtLink></li>
          <li><NuxtLink to="/Contact" class="hover:text-blue-400 font-bold text-xl">Contact</NuxtLink></li>
          <!-- <ThemeToggle /> -->
        </ul>

        <!-- Mobile Menu Button -->
        <button @click="toggleMenu" class="md:hidden">
          <svg class="w-7 h-7" fill="none" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
        </button>
      </nav>
    </div>

    <!-- Mobile Sidebar Menu -->
    <transition name="slide">
      <div v-if="menuOpen" class="fixed top-0 right-0 h-screen w-64 bg-gray-800 shadow-lg z-50 p-6">
        <!-- Close Button -->
        <button @click="closeMenu" class="absolute top-4 right-4 text-white">
          ✕
        </button>

        <ul class="flex flex-col gap-6 mt-12 text-lg font-semibold">
          <li><NuxtLink to="/" @click="closeMenu" class="hover:text-cyan-400">Home</NuxtLink></li>
          <li><NuxtLink to="/Abouts" @click="closeMenu" class="hover:text-cyan-400">About</NuxtLink></li>
          <li><NuxtLink to="/Projects" @click="closeMenu" class="hover:text-cyan-400">Projects</NuxtLink></li>
          <li><NuxtLink to="/Contact" @click="closeMenu" class="hover:text-cyan-400">Contact</NuxtLink></li>
        </ul>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
const toggleMenu = () => menuOpen.value = !menuOpen.value
const closeMenu = () => menuOpen.value = false
</script>

<style>
/* Slide transition */
.slide-enter-active, .slide-leave-active {
  transition: transform 0.3s ease;
}
.slide-enter-from {
  transform: translateX(100%);
}
.slide-leave-to {
  transform: translateX(100%);
}
</style>
