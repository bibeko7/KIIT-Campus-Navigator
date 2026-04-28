<template>
  <div class="min-h-screen mt-6 bg-white">
    <!-- Header -->
    <!-- <header class="pt-8 px-6">
      <p class="text-cyan-400 text-lg font-medium animate-fadeIn">
        Welcome to my site
      </p>
    </header> -->

    <!-- Main Content -->
    <main class="px-6 py-12">
      <div class="max-w-6xl mx-auto">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          
          <!-- Left Content -->
          <div class="space-y-8">
            <!-- Typing Heading -->
            <div>
              <h1 class="text-4xl lg:text-5xl font-bold text-gray-900 leading-tight animate-slideUp">
                Hi, I'm Harendra, a
                <br>
                <span class="text-cyan-500 typewriter">System/Network</span> 
                <span class="text-orange-400"> Software Developer.</span>
              </h1>
            </div>

            <!-- Animated Paragraph -->
            <div class="space-y-4 animate-fadeIn delay-500">
              <p class="text-gray-700 text-lg leading-relaxed">
                I am Harendra Shah, a passionate Software developer and system/network enthusiast, dedicated to creating responsive, user-friendly, and visually engaging web experiences.
                <NuxtLink to="/Abouts" class="text-cyan-500 hover:text-cyan-600 transition-colors">
                  See More..
                </NuxtLink>
              </p>
            </div>

            <!-- Action Buttons -->
            <div class="flex flex-wrap gap-4 animate-stagger">
              <!-- <button class="bg-cyan-500 hover:bg-cyan-600 text-white px-8 py-3 rounded-lg font-medium transition-transform transform hover:scale-105">
                Hire me !
              </button> -->
              <NuxtLink to="/Projects">
              <button class="bg-cyan-500 hover:bg-cyan-600 text-white px-8 py-3 rounded-lg font-medium transition-transform transform hover:scale-105">
                  See My Project
                </button>
              </NuxtLink>
            </div>
          </div>

          <!-- Right Content - Profile Image -->
          <div class="flex justify-center lg:justify-end">
            <div class="relative w-80 h-96 lg:w-96 lg:h-[28rem] animate-imageZoom">
              <!-- Background Shape -->
              <div class="absolute top-2 left-2 w-full h-full rounded-tl-[100px] rounded-bl-[100px] bg-blue-300"></div>

              <!-- Image Box -->
              <div class="relative w-full h-full overflow-hidden rounded-tl-[100px] rounded-bl-[100px] border-2 border-blue-400">
                <img
                  :src="harendra"
                  alt="Profile"
                  class="object-cover w-full h-full"
                />
              </div>
              <div class="mt-4 flex gap-4 justify-center">
    <!-- Open in new tab -->
<!-- Open in new tab -->
<a
  href="/HarendrakShah(cv).pdf"
  target="_blank"
  class="px-6 py-2 bg-cyan-500 text-white rounded-lg font-medium hover:bg-cyan-600 transition-colors"
>
  Open CV
</a>

<!-- Direct download -->
<a
  href="/HarendrakShah(cv).pdf"
  download
  class="px-6 py-2 border-2 border-cyan-500 text-cyan-500 rounded-lg font-medium hover:bg-cyan-50 transition-colors"
>
  Download CV
</a>

  </div>
            </div>
          </div>

        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
import harendra from '~/assets/img/dceditpic.png';
</script>

<style>
/* 🔹 Fade In */
@keyframes fadeIn {
  from { opacity: 0 }
  to { opacity: 1 }
}
.animate-fadeIn {
  animation: fadeIn 1s ease forwards;
}

/* 🔹 Slide Up */
@keyframes slideUp {
  from { opacity: 0; transform: translateY(20px) }
  to { opacity: 1; transform: translateY(0) }
}
.animate-slideUp {
  animation: slideUp 1s ease forwards;
}

/* 🔹 Typing Effect */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}
@keyframes blink {
  50% { border-color: transparent }
}
.typewriter {
  display: inline-block;
  border-right: 2px solid #06b6d4;
  white-space: nowrap;
  overflow: hidden;
  width: 0;
  animation: typing 3s steps(20, end) forwards, blink 0.8s step-end infinite;
}

/* 🔹 Stagger Buttons */
@keyframes stagger {
  0% { opacity: 0; transform: translateY(20px) }
  100% { opacity: 1; transform: translateY(0) }
}
.animate-stagger > * {
  opacity: 0;
  animation: stagger 0.8s ease forwards;
}
.animate-stagger > *:nth-child(1) {
  animation-delay: 0.6s;
}
.animate-stagger > *:nth-child(2) {
  animation-delay: 0.9s;
}

/* 🔹 Image Zoom In */
@keyframes imageZoom {
  from { opacity: 0; transform: scale(0.8) rotate(-2deg) }
  to { opacity: 1; transform: scale(1) rotate(0) }
}
.animate-imageZoom {
  animation: imageZoom 1s ease forwards 0.7s;
}

/* Delay utilities */
.delay-500 {
  animation-delay: 0.5s;
}
</style>
