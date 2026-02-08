<script setup>
import { Icon } from '@iconify/vue';

const certificates = [
  {
    title: 'Azure AZ-900',
    issuer: 'Microsoft',
    date: 'May 2023',
    link: 'https://www.credly.com/badges/7b861dc0-4efa-440f-8ba8-a7eb95784e1c/public_url'
  },
  {
    title: 'Google Cloud Foundations Badges',
    issuer: 'Google',
    date: 'June 2023',
    link: 'https://www.skills.google/public_profiles/85a9776e-2346-4dd2-9ca2-c822f213efe9'
  },
  {
    title: 'Hackatruck Presential Course',
    issuer: 'Eldorado Institute',
    date: 'July 2025',
    link: 'https://ibb.co/SXkQt9rp'
  },
  {
    title: 'ICPC Regional Competitions',
    issuer: 'ICPC',
    date: '2023-2025',
    links: [{name: '2023', link: 'https://ibb.co/QYJ82Sg'}, {name: '2024', link: 'https://ibb.co/yBQyFBPX'}, {name: '🥉2025', link: 'https://ibb.co/JwPWDdhp'}]
  },
  {
    title: 'CS Merit Awards',
    issuer: 'Unoeste',
    date: '2024-2026',
    links: [{name: '🥇2024', link: 'https://ibb.co/djCpT6r'}, {name: '🥈2025', link: 'https://www.unoeste.br/centralassinaturas/doc/info/cc183f08'}, {name: '🥉2025', link: 'https://www.unoeste.br/centralassinaturas/doc/info/d260a988'}, {name: '🥈2026', link: 'https://www.unoeste.br/centralassinaturas/doc/info/e7550288'}]
  }
];
</script>

<template>
    <section class="min-h-screen flex items-center justify-center px-6 py-20">
      <div class="max-w-6xl w-full">
        <h2 class="text-4xl md:text-5xl font-bold text-white mb-12">
          <span class="text-red-600">Certificates</span> & Achievements
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <div 
            class="bg-gray-900 border border-gray-800 rounded-lg p-6 hover:border-red-600 transition-colors flex flex-col justify-between"
            v-for="(certificate, index) in certificates"
            :key="index"
            >
                <div class="flex items-start gap-3 mb-4">
                <div class="p-2 bg-red-600/10 rounded-lg shrink-0">
                    <Icon icon="lucide:award" class="w-6 h-6 text-red-600" />
                </div>
                <div class="flex-1 min-w-0">
                    <h3 class="text-lg font-semibold text-white mb-1">
                        {{certificate.title}}
                    </h3>
                    <p class="text-gray-400 text-sm mb-1">
                        {{certificate.issuer}}
                    </p>
                    <p class="text-gray-500 text-sm">
                        {{certificate.date}}
                    </p>
                </div>
                </div>
                <a 
                v-if="certificate.link"
                :href="certificate.link"
                target="_blank"
                rel="noopener noreferrer"
                class="flex items-center gap-2 text-red-600 hover:text-red-500 transition-colors text-md"
                >
                View Certificate
                <Icon icon="lucide:external-link" class="w-4 h-4" />
                </a>
                <div
                v-else
                class="flex gap-3"
                >
                    <a
                    v-for="link in certificate.links"
                    :href="link.link"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="flex items-center gap-2 text-red-600 hover:text-red-500 transition-colors text-md"
                    >
                        {{ link.name }}
                        <Icon icon="lucide:external-link" class="w-4 h-4" />
                    </a>

                </div>                
            </div>
        </div>
      </div>
    </section>
</template>