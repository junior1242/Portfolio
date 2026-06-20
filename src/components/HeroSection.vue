<template>
  <section id="hero" class="min-h-screen flex items-center px-[5%] pt-24 pb-16 overflow-hidden"
    style="background: linear-gradient(135deg, rgba(124,58,237,0.15) 0%, rgba(10,10,20,0.8) 40%, rgba(59,130,246,0.12) 60%, rgba(10,10,20,0.9) 100%), radial-gradient(circle at 20% 50%, rgba(124,58,237,0.1) 0%, transparent 50%);">
    <div class="max-w-5xl mx-auto w-full flex items-center gap-16">
      <div class="hidden md:flex flex-shrink-0 items-center justify-center animate-fade-in">
        <div
          class="w-[380px] h-[480px] rounded-2xl overflow-hidden shadow-[0_20px_60px_rgba(124,58,237,0.3),0_0_40px_rgba(124,58,237,0.2)] bg-gradient-to-br from-violet-600/20 to-blue-600/20 border border-violet-500/30 group">
          <img src="@/assets/shahidPic.png" alt="Shahid Ali"
            class="w-full h-full object-cover object-center block transition-transform duration-700 group-hover:scale-105" />
        </div>
      </div>

      <div class="flex-1">
        <div
          class="animate-slide-up opacity-0 inline-block bg-gradient-to-r from-violet-900/30 to-blue-900/30 border border-violet-500/50 text-violet-300 px-4 py-1.5 rounded-full text-sm mb-6 w-fit"
          style="animation-delay: 100ms; animation-fill-mode: forwards;">
          ✨ Available for hire
        </div>

        <h1 class="text-[clamp(2.5rem,8vw,6rem)] font-extrabold leading-[1.05] mb-4">
          <span class="inline-block animate-slide-up opacity-0 gradient-text"
            style="animation-delay: 300ms; animation-fill-mode: forwards; padding-bottom: 0.1em;">Full
            Stack</span><br />
          <span class="inline-block animate-slide-up opacity-0 gradient-text"
            style="animation-delay: 450ms; animation-fill-mode: forwards; padding-bottom: 0.1em;">Developer.</span>
        </h1>

        <p class="text-base sm:text-xl text-white/70 mb-10 max-w-[480px] animate-slide-up opacity-0"
          style="animation-delay: 600ms; animation-fill-mode: forwards;">
          I build things for the web — clean, fast, and scalable.
        </p>

        <div class="flex flex-col sm:flex-row gap-4 animate-slide-up opacity-0"
          style="animation-delay: 750ms; animation-fill-mode: forwards;">
          <a href="#projects"
            class="btn-gradient text-white px-8 py-3 rounded-lg font-semibold no-underline transition-all text-center hover:-translate-y-1 hover:shadow-[0_10px_20px_rgba(124,58,237,0.3)]">
            View My Work
          </a>
          <a href="#contact"
            class="btn-gradient-outline text-white px-8 py-3 rounded-lg font-semibold no-underline transition-all text-center hover:text-white hover:-translate-y-1">
            Get In Touch
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Gradient Text Utility */
.gradient-text {
background: #9a92b0;
  background: linear-gradient(90deg, rgba(154, 146, 176, 1) 0%, rgba(137, 127, 168, 1) 30%, rgba(59, 47, 98, 1) 65%, rgba(58, 73, 102, 1) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* Custom Keyframes */
@keyframes slideUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }

  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: scale(0.95);
  }

  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* Utility Classes */
.animate-slide-up {
  animation: slideUp 0.8s cubic-bezier(0.16, 1, 0.3, 1);
}

.animate-fade-in {
  animation: fadeIn 1.2s ease-out forwards;
}
</style>