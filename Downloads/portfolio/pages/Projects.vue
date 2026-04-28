<template>
  <section class="max-w-6xl mx-auto py-16 px-4">
    <h2 class="text-3xl font-bold mb-6 text-center">Projects</h2>
    <div class="grid gap-6 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      
      <div v-for="project in projects" :key="project.title" class="bg-white shadow-md rounded-lg p-4 flex flex-col items-center transition hover:shadow-xl">
        
        <!-- Clickable Logo + Title -->
        <a :href="project.link" target="_blank" class="flex flex-col items-center w-full cursor-pointer">
          <img :src="project.logo" :alt="project.title + ' Logo'" class="w-24 h-24 mb-4 object-contain">
          <h3 class="text-xl font-semibold text-center hover:text-cyan-500">{{ project.title }}</h3>
        </a>

        <!-- Paragraph with See More -->
        <p class="text-gray-600 mt-2 text-center">
          {{ project.shortDescription }}
          <span v-if="project.showFull"> {{ project.fullDescription }} </span>
        </p>
        <button @click="project.showFull = !project.showFull" class="mt-2 text-sm text-cyan-500 hover:underline">
          {{ project.showFull ? 'See Less' : 'See More' }}
        </button>
        
      </div>

    </div>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

import helloSarkar from '~/assets/logos/Hellosarkar.png'
import sociair from '~/assets/logos/sociair.jpg'
import oxbite from '~/assets/logos/oxbitetechnology.png'
import swiftAdvice from '~/assets/logos/swiftadvice.png'
import informaticEdupath from '~/assets/logos/Informaticedupath.png'

const projects = reactive([
  {
    title: 'Hello Sarkar',
    logo: helloSarkar,
    shortDescription: 'Hello Sarkar is a government-led initiative in Nepal designed to strengthen communication between citizens and the government...',
    fullDescription: 'The platform allows people to file complaints, share feedback, and report issues that directly reach the Prime Minister’s Office. I contributed specifically to developing the section that deals with misuse during elections, enabling citizens to report unfair practices and election-related problems effectively. My role was to ensure smooth usability, proper categorization, and better user experience for reporting.',
    link: 'https://gunaso.opmcm.gov.np/home',
    showFull: false
  },
  {
    title: 'Sociair',
    logo: sociair,
    shortDescription: 'Sociair is an AI-powered social networking solution built to help businesses connect, collaborate, and grow their digital presence...',
    fullDescription: 'The platform integrates artificial intelligence for smarter recommendations, improved engagement, and seamless networking opportunities. I worked on implementing the account deletion feature, ensuring privacy and compliance with data standards. Additionally, I contributed to refining the overall UI, making it more user-friendly and responsive across devices. My contributions helped enhance both usability and trust for end users.',
    link: 'https://sociair.com/',
    showFull: false
  },
  {
    title: 'Oxbite Technologies',
    logo: oxbite,
    shortDescription: 'Oxbite Technologies is a global IT solutions provider that delivers web development, cloud services, and innovative tech solutions...',
    fullDescription: 'At Oxbite, I was responsible for handling several critical development tasks independently, including front-end implementation, backend integration, and UI/UX improvements. My work ensured that projects were delivered with high-quality standards and within deadlines. This experience allowed me to strengthen my problem-solving skills while working on real-world, client-focused projects that required creativity and precision.',
    link: 'https://www.oxbite.com/',
    showFull: false
  },
  {
    title: 'SwiftAdvice',
    logo: swiftAdvice,
    shortDescription: 'SwiftAdvice is an Australian financial advisory platform designed to provide personalized investment and financial planning solutions...',
    fullDescription: 'I fully developed and implemented this project, from designing the responsive UI to integrating core functionalities for financial advice services. My focus was on ensuring smooth navigation, secure data handling, and a user experience that builds trust with clients. By completing this project end-to-end, I gained valuable experience in delivering a complete professional platform independently.',
    link: 'https://swiftadvice.com.au/',
    showFull: false
  },
  {
    title: 'Informatic EduPath',
    logo: informaticEdupath,
    shortDescription: 'Informatic EduPath is my own e-learning platform built to offer interactive and responsive online courses...',
    fullDescription: 'I fully designed and developed the platform, focusing on user-friendly navigation, modern design, and accessibility across devices. The goal of EduPath is to provide a simple yet effective space for learners to explore courses, track progress, and engage in digital education. Developing this project gave me complete control over both front-end and backend aspects of an educational platform.',
    link: 'https://informaticedupath.netlify.app/',
    showFull: false
  }
])
</script>
