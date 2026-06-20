<template>
  <section id="projects"
    style="background: linear-gradient(100deg, rgba(10,10,20,0.9) 0%, rgba(139,92,246,0.08) 30%, rgba(59,130,246,0.08) 70%, rgba(10,10,20,0.9) 100%), radial-gradient(circle at 80% 80%, rgba(236,72,153,0.08) 0%, transparent 50%);"
    class="py-24 px-[5%]">
    <div class="max-w-5xl mx-auto">
      <div
        class="text-xs uppercase tracking-[2px] bg-gradient-to-r from-violet-600 to-blue-600 bg-clip-text text-transparent font-semibold mb-3">
        Work</div>
      <h2 class="text-[clamp(2rem,4vw,2.75rem)] font-extrabold leading-tight gradient-text">Featured Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-10">
        <div v-for="project in projects" :key="project.title" class="card-gradient rounded-xl p-8">
          <h3 class="text-white font-bold text-xl mb-3">{{ project.title }}</h3>
          <p class="text-white/60 text-sm leading-relaxed mb-6 text-justify">{{ project.description }}</p>
          <div class="flex flex-wrap items-center gap-3">
            <a v-if="project.demo && project.demo !== '#'" :href="project.demo"
              class="text-violet-400 hover:text-white text-sm font-medium no-underline transition-colors"
              target="_blank" rel="noopener">
              ↗ Live Demo
            </a>
            <span v-else class="text-white/35 text-sm font-medium cursor-not-allowed select-none" aria-disabled="true">
              Live Demo unavailable
            </span>

            <a :href="project.github"
              class="text-violet-400 hover:text-white text-sm font-medium no-underline transition-colors"
              target="_blank" rel="noopener">
              ↗ GitHub
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'GCB-FEST',
    description: 'A dynamic event management platform built using MERN Stack, designed to streamline event organization and enhance attendee engagement.',
    demo: 'https://gcb-fest-frontend.onrender.com',
    github: 'https://github.com/junior1242/gcb-fest',
  },
  {
    title: 'Blog',
    description: 'A personal blogging platform built with Vue.js and Frappe, allowing users to create, edit, and share their thoughts.',
    demo: '#',
    github: 'https://github.com/junior1242/blog',
  },
  {
    title: 'Simple GPA Calculator',
    description: 'A straightforward GPA calculator for students to compute their cumulative grade point average.',
    demo: '#',
    github: 'https://github.com/junior1242/GPACalculator',
  },
]
</script>
