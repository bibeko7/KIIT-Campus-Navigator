<template>
  <div class="min-h-screen bg-gradient-to-br from-cyan-50 via-white to-gray-100 px-6 py-12">
    <div class="max-w-5xl mx-auto bg-white shadow-xl rounded-2xl overflow-hidden">
      
      <!-- Header -->
      <div class="bg-cyan-500 text-white py-8 px-6 text-center">
        <h1 class="text-3xl sm:text-4xl font-bold">Contact Me</h1>
        <p class="mt-2 text-cyan-100">Get in touch, I’d love to hear from you</p>
      </div>

      <!-- Content -->
      <div class="p-6 sm:p-10 lg:flex lg:gap-12">
        
        <!-- Left: Contact Info + Form -->
        <div class="lg:w-1/2 space-y-6">

          <!-- Contact Info -->
          <div class="flex items-center gap-3">
            <span class="text-cyan-500 text-xl">👤</span>
            <span class="text-gray-900 font-medium">Harendra Shah</span>
          </div>
          <div class="flex items-center gap-3">
            <span class="text-cyan-500 text-xl">📞</span>
            <div class="flex flex-col text-gray-900">
              <a href="tel:+9779826731085" class="hover:text-cyan-600">+977 9826731085</a>
              <a href="tel:+9779746600424" class="hover:text-cyan-600">+977 9746600424</a>
            </div>
          </div>
          <div class="flex items-center gap-3">
            <span class="text-cyan-500 text-xl">📧</span>
            <a href="mailto:sahh8645@gmail.com" class="text-gray-900 hover:text-cyan-600">sahh8645@gmail.com</a>
          </div>
          <div class="flex items-center gap-3">
            <span class="text-cyan-500 text-xl">📍</span>
            <span class="text-gray-900">Lalitpur, Nepal</span>
          </div>

          <!-- Contact Form -->
          <form @submit.prevent="submitForm" class="mt-6 space-y-4">

            <div class="flex gap-4">
              <input v-model="form.firstName" type="text" placeholder="First Name" required
                class="w-1/2 px-4 py-2 border rounded-lg focus:ring-2 focus:ring-cyan-400 focus:outline-none"/>
              <input v-model="form.lastName" type="text" placeholder="Last Name" required
                class="w-1/2 px-4 py-2 border rounded-lg focus:ring-2 focus:ring-cyan-400 focus:outline-none"/>
            </div>

            <input v-model="form.email" type="email" placeholder="Email" required
              class="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-cyan-400 focus:outline-none"/>
            <input v-model="form.phone" type="tel" placeholder="Phone" required
              class="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-cyan-400 focus:outline-none"/>
            <textarea v-model="form.message" placeholder="Message" rows="4" required
              class="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-cyan-400 focus:outline-none"></textarea>

            <button type="submit" class="w-full px-6 py-3 bg-cyan-500 text-white rounded-lg font-medium shadow hover:bg-cyan-600 transition-colors flex justify-center items-center"
              :disabled="loading">
              <span v-if="loading">Sending...</span>
              <span v-else>Submit</span>
            </button>
          </form>

        </div>

        <!-- Right: Google Map -->
        <div class="lg:w-1/2 mt-10 lg:mt-0">
          <div class="w-full h-80 sm:h-96 rounded-xl overflow-hidden shadow-lg border border-cyan-100">
            <iframe class="w-full h-full" :src="mapUrl" style="border:0;" allowfullscreen="" loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"></iframe>
          </div>
        </div>

      </div>
    </div>

    <!-- Success Modal -->
    <div v-if="success" class="fixed inset-0 bg-black bg-opacity-40 flex justify-center items-center z-50">
      <div class="bg-white p-6 rounded-xl shadow-xl text-center space-y-4">
        <h2 class="text-xl font-bold text-green-600">Message Sent!</h2>
        <p>Thank you, I will get back to you soon.</p>
        <button @click="success=false" class="px-4 py-2 bg-cyan-500 text-white rounded-lg hover:bg-cyan-600">Close</button>
      </div>
    </div>

  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

// Google Map
const mapUrl = "https://www.google.com/maps/embed?pb=!4v1724753215!6m8!1m7!1sCAoSLEFGMVFpcE1nWlpObkRWeDFpVGRNcmg3ZnQ0XzhtdmNYb2hMUDZZUGg0amY4!2m2!1d27.6455879!2d85.3448016!3f0!4f0!5f0.7820865974627469"

// Form reactive
const form = reactive({
  firstName: '',
  lastName: '',
  email: '',
  phone: '',
  message: ''
})

const loading = ref(false)
const success = ref(false)

const submitForm = async () => {
  if (!form.firstName || !form.lastName || !form.email || !form.phone || !form.message) return
  loading.value = true
  try {
    const formData = new FormData()
    formData.append('firstName', form.firstName)
    formData.append('lastName', form.lastName)
    formData.append('email', form.email)
    formData.append('phone', form.phone)
    formData.append('message', form.message)

    const response = await fetch('https://formspree.io/f/myzebpgb', {
      method: 'POST',
      body: formData,
      headers: {
        Accept: 'application/json'
      }
    })

    if (response.ok) {
      success.value = true
      // Reset form
      form.firstName = ''
      form.lastName = ''
      form.email = ''
      form.phone = ''
      form.message = ''
    } else {
      alert('Something went wrong. Please try again later.')
    }
  } catch (error) {
    console.error(error)
    alert('Failed to send message. Try again.')
  } finally {
    loading.value = false
  }
}
</script>
