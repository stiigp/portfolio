<script setup>
import { Icon } from '@iconify/vue';

let competences = [
    {
        icon: 'server',
        title: 'Backend Development',
        skills: ['FastAPI', 'Spring Boot', 'Express', 'REST APIs']
    },
    {
        icon: 'database',
        title: 'Databases',
        skills: ['PostgreSQL', 'MySQL', 'Oracle', 'ElasticSearch']
    },
    {
        icon: 'code',
        title: 'Frontend Development',
        skills: ['Vue', 'React', 'Javascript', 'Tailwind CSS']
    },
    {
        icon: 'git-branch',
        title: 'DevOps & Tools',
        skills: ['Git', 'Docker', 'Linux']
    },
    {
        icon: 'smartphone',
        title: 'Mobile Development',
        skills: ['Java Android', 'SwiftUI']
    }
]

const lucide = (iconName) => {
    return "lucide:"+iconName
}

const scrollToContent = () => {
  window.scrollTo({
    top: window.innerHeight*2,
    behavior: 'smooth'
  });
};

</script>

<template>
    <section class="min-h-screen flex items-center justify-center px-6 py-20">
      <div class="max-w-6xl w-full">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-12">
          <span class="text-red-600">Competences</span> & Skills
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <div 
            v-for="(competence, index) in competences"
            :key="index"
            class="bg-gray-900 border border-gray-800 rounded-lg p-6 hover:border-red-600 transition-colors"
            >
            <div class="flex items-center gap-3 mb-4">
                <div class="p-2 bg-red-600/10 rounded-lg">
                <Icon :icon=lucide(competence.icon) class="w-6 h-6 text-red-600" />
                </div>
                <h3 class="text-xl font-semibold text-white">
                    {{ competence.title }}
                </h3>
            </div>
            <div class="flex flex-wrap gap-2">
                <span 
                    class       ="px-3 py-1 bg-gray-800 text-gray-300 rounded-full text-sm"
                    v-for="(skill, skillIndex) in competence.skills"
                    :key="skillIndex"
                >
                    {{skill}}
                </span>
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