<template>
  <section class="relative text-center py-20 px-6 bg-gradient-to-br from-cyan-50 via-white to-gray-100 overflow-hidden">
    <!-- Animated Background Circles -->
    <span class="absolute top-0 left-1/2 w-72 h-72 bg-blue-200 rounded-full opacity-30 animate-pulse -translate-x-1/2 -translate-y-1/2"></span>
    <span class="absolute bottom-0 right-1/4 w-96 h-96 bg-purple-200 rounded-full opacity-20 animate-pulse translate-x-1/2 translate-y-1/2"></span>

    <!-- Header -->
    <h2 class="text-4xl sm:text-5xl font-bold mb-4 text-gray-800 animate-fadeInUp">
      Hi, I'm Harendra 👋
    </h2>
    <p class="text-lg sm:text-xl text-gray-700 max-w-3xl mx-auto mb-8 animate-fadeInUp delay-150">
      I am <strong>Harendra Kumar Shah</strong>, a frontend developer, system/network enthusiast, and Software Developer of <strong>Informatic EduPath</strong>. I create responsive, user-friendly, and visually engaging web experiences. Skilled in <strong>Nuxt.js, Vue.js, and Tailwind CSS</strong>, I turn ideas into functional and elegant digital solutions. On the systems and network side, I manage Active Directory users, deploy monitoring tools like LibreNMS and Zabbix, handle switches from Cisco and MikroTik, and implement software restrictions and firewalls using Fortinet and Sophos. Always learning, I aim to build applications and infrastructures that are technically solid and seamless across all devices.
    </p>

    <!-- Education Card -->
    <div class="mt-10 max-w-2xl mx-auto text-left bg-white shadow-xl rounded-2xl p-6 sm:p-8 animate-fadeInUp delay-300">
      <h3 class="text-2xl font-semibold mb-4 text-center text-gray-800">Education 🎓</h3>
      <ul class="space-y-3 text-gray-700 text-base sm:text-lg">
        <li>
          <strong>BSc (Hons) CIT</strong> – AITM College, Kathmandu
        </li>
        <li>
          <strong>+2 Computer Science</strong> – Bridgewater International College, Sinamangal, Kathmandu
        </li>
        <li>
          <strong>SEE</strong> – Little Star English School, Lahan, Siraha
        </li>
      </ul>
    </div>

    <!-- Projects Button -->
    <NuxtLink to="/Projects" 
      class="mt-8 inline-block px-8 py-3 bg-blue-600 text-white font-medium rounded-xl shadow-lg hover:bg-blue-700 transform hover:scale-105 transition duration-300 animate-fadeInUp delay-500">
      View My Work
    </NuxtLink>
  </section>
</template>

<style>
/* Custom Animations */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.animate-fadeInUp {
  animation: fadeInUp 0.8s ease forwards;
}
.delay-150 {
  animation-delay: 0.15s;
}
.delay-300 {
  animation-delay: 0.3s;
}
.delay-500 {
  animation-delay: 0.5s;
}
</style>
