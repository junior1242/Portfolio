<template>
  <section id="skills" style="background: linear-gradient(135deg, rgba(10,10,20,0.95) 0%, rgba(26,10,46,0.8) 40%, rgba(59,130,246,0.1) 70%, rgba(10,10,20,0.95) 100%), radial-gradient(circle at 20% 80%, rgba(124,58,237,0.12) 0%, transparent 50%);" class="py-24 px-[5%]">
    <div class="max-w-5xl mx-auto">
      <div class="text-xs uppercase tracking-[2px] bg-gradient-to-r from-violet-600 to-blue-600 bg-clip-text text-transparent font-semibold mb-3">Expertise</div>
      <h2 class="text-[clamp(2rem,4vw,2.75rem)] font-extrabold leading-tight gradient-text">My Technical Toolkit</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-10">
        <div
          v-for="cat in categories"
          :key="cat.title"
          class="card-gradient rounded-xl p-8"
        >
          <h3 class="text-white font-bold text-lg mb-3">{{ cat.title }}</h3>
          <p class="text-white/60 text-sm leading-relaxed mb-6 text-justify">{{ cat.desc }}</p>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="tag in cat.tags"
              :key="tag"
              class="bg-gradient-to-r from-violet-900/40 to-blue-900/40 border border-violet-500/50 text-violet-300 px-3 py-1 rounded-full text-xs font-medium"
            >{{ tag }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const categories = [
  {
    title: 'ERP & Business Solutions',
    desc: 'Building and customizing business applications using Frappe framework and ERPNext.',
    tags: ['Frappe', 'ERPNext', 'Vue.js', 'Python'],
  },
  {
    title: 'Frontend',
    desc: 'Building fast, responsive interfaces with React and modern JavaScript.',
    tags: ['React', 'JavaScript', 'HTML', 'CSS'],
  },
  {
    title: 'Backend',
    desc: 'Building RESTful APIs and server-side applications with Node.js and MongoDB.',
    tags: ['Node.js', 'Express', 'MongoDB', 'REST API'],
  },
]
</script>
