<template>
  <div class="relative min-h-screen bg-gray-50 dark:bg-gray-900 transition-colors">
    <!-- Background Watermark -->
    <div class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/cubes.png')] opacity-10"></div>
    
    <!-- Main Content -->
    <div class="relative z-10 flex flex-col min-h-screen">
      <div class="flex justify-end p-4">
        <!-- <ThemeToggle /> -->
      </div>
      <HeaderPage />
              <!-- <ThemeToggle /> -->

      <main class="flex-1">
        <NuxtPage />
      </main>
      <Footer />
    </div>
  </div>
</template>

<script setup>
import HeaderPage from '@/components/HeaderPage.vue'
import Footer from '@/components/Footer.vue'
// import ThemeToggle from '@/components/ThemeToggle.vue'
</script>
