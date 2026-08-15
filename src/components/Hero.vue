<script setup>
import { Icon } from '@iconify/vue';

const scrollToContent = () => {
  window.scrollTo({
    top: window.innerHeight,
    behavior: 'smooth'
  });
};
</script>

<template>
    <section class="min-h-screen flex items-center justify-center px-6 py-20">
      <div class="max-w-4xl w-full">
        <div class="space-y-6 text-center flex flex-col items-center">
          <h1 class="animating-name text-5xl md:text-7xl font-bold text-white w-full">
            Lucas <span class="text-red-600">Panucci</span>
          </h1>
          <h2 class="animating-ft text-2xl md:text-3xl text-gray-400 w-full max-w-full sm:max-w-2xl mx-auto">
            CS Student: Development & Data
          </h2>
          <p class="animating-st text-lg text-gray-300 w-full max-w-full">
            Passionate developer with particular interest for Backend solutions and Data/Machine Learning
          </p>
          <div class="flex gap-4 pt-4 justify-center">
            <a 
              href="https://github.com/stiigp" 
              target="_blank" 
              rel="noopener noreferrer"
              class="p-3 bg-gray-900 hover:bg-red-600 transition-colors rounded-lg"
            >
              <Icon icon="lucide:github" class="w-6 h-6 text-white" />
            </a>
            <a 
              href="https://www.linkedin.com/in/lucas-panucci-94823320b/"
              target="_blank" 
              rel="noopener noreferrer"
              class="p-3 bg-gray-900 hover:bg-red-600 transition-colors rounded-lg"
            >
              <Icon icon="lucide:linkedin" class="w-6 h-6 text-white" />
            </a>
            <a 
              href="mailto:lucaspanuccidev@gmail.com"
              class="p-3 bg-gray-900 hover:bg-red-600 transition-colors rounded-lg"
            >
              <Icon icon="lucide:mail" class="w-6 h-6 text-white" />
            </a>
          </div>
          <a 
          target="_blank"
          rel="noopener noreferrer"
          class="flex items-center w-45 gap-2 px-4 py-2 bg-red-600 hover:bg-red-700 text-white rounded-lg transition-colors mx-auto"
          href="/cv.pdf"
          download="LUCAS_PANUCCI_CV.pdf"
          >
              <Icon icon="lucide:download" class="w-6 h-6 text-gray-200" />
              <span class="text-gray-200">Download Resume</span>
          </a>
          <div class="pt-12 flex flex-col items-center gap-2 opacity-80 hover:opacity-100 transition-opacity cursor-pointer" @click="scrollToContent">
            <span class="text-lg uppercase tracking-widest text-gray-400">Scroll</span>
            <Icon icon="lucide:chevron-down" class="w-6 h-6 text-red-600" />
          </div>
        </div>
      </div>
    </section>
</template>