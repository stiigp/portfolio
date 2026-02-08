<script setup>
import { Icon } from '@iconify/vue';

const projects = [
    {
        title: 'Hybrid Recommender System',
        description: 'A Movie Recommender System built combining Content-Based and Collaborative Filtering using Elasticsearch and Implicit in Python',
        technologies: ['FastAPI', 'Elasticsearch', 'Data Science', 'Implicit', 'PostgreSQL', 'Vue'],
        github: 'https://github.com/stiigp/portf-recsys',
        live: 'https://recsys.panucci.cloud'
    },
    {
        title: 'MLP From Scratch',
        description: 'An artificial neural network (specifically a multi-layered perceptron) built from scratch using Java',
        technologies: ['Java', 'Machine Learning', 'Spring Boot', 'Server-Sent Events', 'React'],
        github: 'https://github.com/stiigp/mlp-java/',
        live: null
    },
    {
        title: 'Titanic Kaggle Competition',
        description: 'My submissions to the Titanic Machine Learning Competition from Kaggle',
        technologies: ['Data Engineering', 'Python', 'Pandas', 'Kaggle'],
        github: 'https://github.com/stiigp/kaggle-titanic-competition',
        live: null
    },
    {
        title: 'FippMarket',
        description: 'A Fullstack Web-Commerce Simulator built using Java Spring Boot and Vue.js',
        technologies: ['Java', 'Spring Boot', 'Vue.js', 'JWT', 'PostgreSQL'],
        github: 'https://github.com/stiigp/MercadoFipp',
        live: null
    },
];

const scrollToContent = () => {
  window.scrollTo({
    top: window.innerHeight*3.2,
    behavior: 'smooth'
  });
};
</script>


<template>
    <section class="min-h-screen flex items-center justify-center px-6 py-20">
      <div class="max-w-6xl w-full">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-12">
          Featured <span class="text-red-600">Projects</span>
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div
                v-for="(project, index) in projects"
                :key=index
                class="bg-gray-900 border border-gray-800 rounded-lg p-6 hover:border-red-600 transition-colors"
            >
                <h3 class="text-2xl font-semibold text-white mb-3">
                    {{project.title}}
                </h3>
                <p class="text-gray-400 mb-4">
                    {{project.description}}
                </p>
                <div class="flex flex-wrap gap-2 mb-4">
                    <span 
                    v-for="(tech, techIndex) in project.technologies"
                    :key=techIndex
                    class="px-3 py-1 bg-red-600/10 text-red-400 rounded-full text-sm"
                    >
                        {{tech}}
                    </span>
                </div>
                <div class="flex gap-3">
                    <a 
                        :href="project.github"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="flex items-center gap-2 px-4 py-2 bg-gray-800 hover:bg-gray-700 text-white rounded-lg transition-colors"
                    >
                        <Icon icon="lucide:github" class="w-4 h-4" />
                        Code
                    </a>
                    <a 
                    v-if="project.live"
                    :href="project.live"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="flex items-center gap-2 px-4 py-2 bg-red-600 hover:bg-red-700 text-gray-300 rounded-lg transition-colors"
                    >
                        <Icon icon="lucide:external-link" class="text-gray-200 w-4 h-4" />
                        <span class="text-gray-200">Live Demo</span>
                    </a>
                </div>
            </div>
            
        </div>
        <div class="pt-12 flex flex-col items-center gap-2 opacity-80 hover:opacity-100 transition-opacity cursor-pointer" @click="scrollToContent">
            <span class="text-lg uppercase tracking-widest text-gray-400">Scroll</span>
            <Icon icon="lucide:chevron-down" class="w-6 h-6 text-red-600" />
        </div>
      </div>
    </section>
</template>
