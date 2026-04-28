<template>
  <footer class="bg-gray-900 text-gray-300 py-10 mt-16">
    <div class="max-w-6xl mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8">
      
      <!-- Brand -->
    <div>
  <h2 class="text-xl font-bold text-white">Harendra Kumar Shah</h2>
  <p class="mt-3 text-gray-400 text-sm">
    System & Network • Frontend Developer <br>
    Software Developer of Informatic EduPath
  </p>
</div>


      <!-- Quick Links -->
      <div>
        <h3 class="text-lg font-semibold text-white mb-3">Quick Links</h3>
        <ul class="space-y-2">
          <li><NuxtLink to="/" class="hover:text-white">Home</NuxtLink></li>
          <li><NuxtLink to="/Projects" class="hover:text-white">Projects</NuxtLink></li>
          <li><NuxtLink to="/Contact" class="hover:text-white">Contact</NuxtLink></li>
        </ul>
      </div>

      <!-- Social Links -->
      <div>
        <h3 class="text-lg font-semibold text-white mb-3">Connect</h3>
        <div class="flex space-x-4">
          <a href="https://github.com/Harendrashah" target="_blank" class="hover:text-white">
            <i class="fab fa-github text-2xl"></i>
          </a>
          <a href="https://www.linkedin.com/in/harendra-sah-16692a279/" target="_blank" class="hover:text-white">
            <i class="fab fa-linkedin text-2xl"></i>
          </a>
          <a href="https://x.com/Harendr_shah" target="_blank" class="hover:text-white">
            <i class="fab fa-twitter text-2xl"></i>
          </a>
          <a href="https://www.facebook.com/Harendra.k.shah/" target="_blank" class="hover:text-white">
            <i class="fab fa-facebook text-2xl"></i>
          </a>
        </div>
      </div>
    </div>

    <!-- Bottom -->
    <div class="border-t border-gray-700 mt-8 pt-4 text-center text-sm text-gray-500">
      © {{ new Date().getFullYear() }} Harendra Kumar Shah. All rights reserved.
    </div>
  </footer>
</template>
