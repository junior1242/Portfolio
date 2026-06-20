<template>
  <section id="contact" style="background: linear-gradient(120deg, rgba(10,10,20,0.95) 0%, rgba(26,10,46,0.7) 30%, rgba(124,58,237,0.1) 60%, rgba(10,10,20,0.95) 100%), radial-gradient(circle at 30% 20%, rgba(59,130,246,0.12) 0%, transparent 50%);" class="py-24 px-[5%]">
    <div class="max-w-5xl mx-auto">
      <div class="text-xs uppercase tracking-[2px] bg-gradient-to-r from-violet-600 to-blue-600 bg-clip-text text-transparent font-semibold mb-3">Contact</div>
      <h2 class="text-[clamp(2rem,4vw,2.75rem)] font-extrabold leading-tight gradient-text">
        Let's build<br />something great.
      </h2>
      <p class="text-white/70 text-base leading-relaxed max-w-lg mt-4 mb-10 text-justify">
        I'm currently open to new opportunities — full-time roles or freelance projects. If you have something in mind, I'd love to hear from you.
      </p>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-16 items-start">
        <div class="flex flex-col gap-5">
          <a v-for="link in links" :key="link.label" :href="link.href" class="flex items-center gap-3 text-white/75 hover:text-violet-400 no-underline text-[0.95rem] transition-colors" target="_blank" rel="noopener">
            <span class="w-8 h-8 bg-gradient-to-r from-violet-900/40 to-blue-900/40 border border-violet-500/50 rounded-lg flex items-center justify-center text-violet-400 text-sm shrink-0">{{ link.icon }}</span>
            <span>{{ link.label }}</span>
          </a>
        </div>
        <form class="flex flex-col gap-4" @submit.prevent="handleSubmit">
          <input v-model="form.name" type="text" placeholder="Your Name" required
            class="bg-white/5 border border-white/10 hover:border-violet-600/50 rounded-lg px-4 py-3 text-white text-[0.95rem] outline-none transition-colors placeholder:text-white/35" />
          <input v-model="form.email" type="email" placeholder="Your Email" required
            class="bg-white/5 border border-white/10 hover:border-violet-600/50 rounded-lg px-4 py-3 text-white text-[0.95rem] outline-none transition-colors placeholder:text-white/35" />
          <textarea v-model="form.message" placeholder="Your Message" rows="5" required
            class="bg-white/5 border border-white/10 hover:border-violet-600/50 rounded-lg px-4 py-3 text-white text-[0.95rem] outline-none transition-colors placeholder:text-white/35 resize-y font-[inherit]"></textarea>

          <!-- Status messages -->
          <p v-if="status === 'success'" class="text-green-400 text-sm text-center">
            ✅ Message sent! I'll get back to you soon.
          </p>
          <p v-else-if="status === 'error'" class="text-red-400 text-sm text-center">
            ❌ Something went wrong. Please try again.
          </p>

          <button type="submit" :disabled="loading"
            class="btn-gradient text-white border-none py-3 rounded-lg text-base font-semibold cursor-pointer transition-all disabled:opacity-60 disabled:cursor-not-allowed">
            {{ loading ? 'Sending…' : 'Send Message' }}
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const ACCESS_KEY = import.meta.env.VITE_FORM_ID

const form = reactive({ name: '', email: '', message: '' })
const loading = ref(false)
const status = ref(null) // null | 'success' | 'error'

const links = [
  { href: 'mailto:shahid68491@gmail.com', icon: '✉', label: 'shahid68491@gmail.com' },
  { href: 'https://wa.me/923170150310', icon: '📱', label: '+92 317 0150310' },
  { href: 'https://github.com/junior1242', icon: '⌥', label: 'github.com/junior1242' },
  { href: 'https://www.linkedin.com/in/shahid-ali-636b30376', icon: 'in', label: 'linkedin.com/in/shahid-ali' },
]

async function handleSubmit() {
  loading.value = true
  status.value = null

  try {
    const res = await fetch('https://api.web3forms.com/submit', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json', Accept: 'application/json' },
      body: JSON.stringify({
        access_key: ACCESS_KEY,
        name: form.name,
        email: form.email,
        message: form.message,
      }),
    })

    const data = await res.json()

    if (res.ok && data.success) {
      status.value = 'success'
      form.name = ''
      form.email = ''
      form.message = ''
    } else {
      status.value = 'error'
    }
  } catch {
    status.value = 'error'
  } finally {
    loading.value = false
  }
}
</script>
