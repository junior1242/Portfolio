<template>
  <div class="fixed top-0 left-0 right-0 z-50 flex justify-center px-2 py-3 transition-all duration-300">
    <nav
      class="flex items-center justify-between w-[calc(100%-1rem)] sm:w-full max-w-5xl px-3 sm:px-6 md:px-8 py-2 sm:py-4 rounded-full transition-all duration-300 relative"
      :class="isScrolled || menuOpen
        ? 'shadow-[0_0_60px_rgba(124,58,237,0.4),inset_0_0_30px_rgba(124,58,237,0.1)] backdrop-blur-xl border-2 border-violet-500/60 bg-[rgba(10,10,20,0.3)]'
        : 'bg-transparent'">
      <a href="#hero"
        class="text-base sm:text-lg md:text-xl font-bold bg-linear-to-r from-white to-violet-400 bg-clip-text text-transparent no-underline tracking-wide hover:opacity-80 transition-opacity">
        <span class="sm:hidden">SA</span>
        <span class="hidden sm:inline">Shahid Ali</span>
      </a>

      <!-- Desktop nav -->
      <ul class="hidden md:flex gap-8 lg:gap-12 list-none m-0 p-0">
        <li v-for="link in links" :key="link">
          <a :href="`#${link.toLowerCase()}`"
            class="text-white/75 no-underline text-sm lg:text-[0.95rem] hover:text-violet-400 transition-colors font-medium">{{
            link }}</a>
        </li>
      </ul>
      <a href="#contact"
        class="hidden md:block btn-gradient text-white px-5 lg:px-6 py-2 rounded-full text-xs lg:text-sm font-semibold no-underline transition-all">Hire
        Me</a>

      <!-- Hamburger -->
      <button class="md:hidden flex flex-col gap-1.5 cursor-pointer bg-transparent border-none p-0"
        @click="menuOpen = !menuOpen" aria-label="Toggle menu" :aria-expanded="menuOpen">
        <span class="block w-5 h-0.5 bg-white transition-all duration-300"
          :class="menuOpen ? 'rotate-45 translate-y-2' : ''"></span>
        <span class="block w-5 h-0.5 bg-white transition-all duration-300" :class="menuOpen ? 'opacity-0' : ''"></span>
        <span class="block w-5 h-0.5 bg-white transition-all duration-300"
          :class="menuOpen ? '-rotate-45 -translate-y-2' : ''"></span>
      </button>
    </nav>
  </div>

  <!-- Mobile menu -->
  <div v-if="menuOpen"
    class="fixed top-17 left-2 right-2 z-40 bg-linear-to-b from-[rgba(10,10,20,0.95)] to-violet-900/20 backdrop-blur-xl flex flex-col px-4 py-5 gap-4 md:hidden rounded-3xl border border-violet-500/30 shadow-[0_8px_32px_rgba(124,58,237,0.2)]">
    <a v-for="link in links" :key="link" :href="`#${link.toLowerCase()}`"
      class="text-white/80 hover:text-violet-400 no-underline text-base font-medium transition-colors py-1.5"
      @click="menuOpen = false">{{ link }}</a>
    <a href="#contact"
      class="btn-gradient text-white px-5 py-2.5 rounded-full text-sm font-semibold no-underline transition-all text-center mt-1"
      @click="menuOpen = false">Hire Me</a>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const links = ['About', 'Skills', 'Projects', 'Contact']
const isScrolled = ref(false)
const menuOpen = ref(false)

function onScroll() { isScrolled.value = window.scrollY > 50 }
onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>
