<script setup>
import Hero from './components/Hero.vue'
import Competences from './components/Competences.vue'
import Projects from './components/Projects.vue'
import Certificates from './components/Certificates.vue'
</script>

<template>
  <div class="bg-black w-full">
      <Hero />
      <Competences />
      <Projects />
      <Certificates />
      
      <footer class="border-t border-gray-900 py-8">
        <div class="max-w-6xl mx-auto px-6 text-center text-gray-500">
          <p>© 2026 Lucas Panucci. All rights reserved.</p>
        </div>
      </footer>
    </div>
</template>
