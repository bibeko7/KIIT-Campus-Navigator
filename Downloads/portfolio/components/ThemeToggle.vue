<template>
  <button 
    @click="toggleTheme" 
    class="p-2 rounded-full bg-gray-200 dark:bg-gray-700 transition"
  >
    <span v-if="isDark">🌞</span>
    <span v-else>🌙</span>
  </button>
</template>

<script setup>
import { ref, onMounted } from "vue"

const isDark = ref(false)

onMounted(() => {
  if (localStorage.theme === "dark" || 
      (!("theme" in localStorage) && window.matchMedia("(prefers-color-scheme: dark)").matches)) {
    document.documentElement.classList.add("dark")
    isDark.value = true
  }
})

const toggleTheme = () => {
  isDark.value = !isDark.value
  if (isDark.value) {
    document.documentElement.classList.add("dark")
    localStorage.theme = "dark"
  } else {
    document.documentElement.classList.remove("dark")
    localStorage.theme = "light"
  }
}
</script>
