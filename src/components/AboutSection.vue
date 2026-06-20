<template>
  <section id="about"
    style="background: linear-gradient(110deg, rgba(10,10,20,0.9) 0%, rgba(124,58,237,0.08) 35%, rgba(59,130,246,0.08) 65%, rgba(10,10,20,0.9) 100%), radial-gradient(circle at 80% 20%, rgba(139,92,246,0.1) 0%, transparent 40%);"
    class="py-24 px-[5%]">
    <div class="max-w-5xl mx-auto">

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-10 lg:gap-12 items-center">

        <div>
          <div
            class="text-xs uppercase tracking-[2px] bg-gradient-to-r from-violet-600 to-blue-600 bg-clip-text text-transparent font-semibold mb-3">
            About Me</div>
          <h2 class="text-[clamp(2rem,4vw,2.75rem)] font-extrabold font-justify leading-tight gradient-text mb-6">
            A developer <br /> who loves building <br /> for the web.
          </h2>

          <div class="space-y-4">
            <p class="text-white/70 leading-relaxed text-[1.05rem] text-justify">
              Full Stack Developer with 2+ years of experience building web applications — from
              scalable APIs to responsive interfaces.
            </p>
            <p class="text-white/70 leading-relaxed text-[1.05rem] text-justify">
              I work with modern web technologies and also specialize in Frappe and ERPNext for
              business solutions.
            </p>
          </div>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div v-for="item in details" :key="item.label" class="card-gradient rounded-xl p-6">
            <div
              class="text-[0.75rem] uppercase tracking-widest bg-gradient-to-r from-violet-600 to-blue-600 bg-clip-text text-transparent font-bold mb-2">
              {{ item.label }}</div>
            <div class="text-white/85 text-[0.85rem]">{{ item.value }}</div>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
const details = [
  { label: 'Education', value: 'BS Information Technology' },
  { label: 'Specialties', value: 'Frappe & ERPNext' },
  { label: 'Location', value: 'Lahore, Pakistan' },
  { label: 'Interests', value: 'Continuous Learning & Self-Improvement' },
]
</script>