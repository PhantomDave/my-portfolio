<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

type NavigationItem = {
  label: string
  href: string
}

const props = defineProps<{ navigation: NavigationItem[] }>()

const isMenuOpen = ref(false)
const hasScrolled = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const handleScroll = () => {
  hasScrolled.value = window.scrollY > 12
}

onMounted(() => {
  handleScroll()
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header :class="['fixed inset-x-0 top-0 z-40 transition-all duration-300', hasScrolled ? 'backdrop-blur-lg bg-slate-950/70 border-b border-white/10' : 'bg-transparent border-b border-transparent']">
    <nav class="mx-auto flex max-w-6xl items-center justify-between gap-6 px-6 py-5 text-sm sm:px-8 lg:px-12">
      <a href="#top" class="group flex items-center gap-3 font-medium tracking-tight">
        <span class="relative text-lg text-slate-200">
          Davide Rodo
          <span class="absolute -bottom-1 left-0 h-[2px] w-full scale-x-0 bg-gradient-to-r from-sky-400 to-emerald-400 transition-transform duration-300 group-hover:scale-x-100" />
        </span>
        <span class="hidden rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs text-slate-300 sm:inline-flex">Portfolio 2025</span>
      </a>

      <button
        class="relative inline-flex h-9 w-9 items-center justify-center rounded-full border border-white/10 bg-white/5 text-slate-200 outline-none ring-sky-400 transition hover:border-white/30 hover:bg-white/10 focus-visible:ring md:hidden"
        type="button"
        @click="toggleMenu"
        :aria-expanded="isMenuOpen"
        aria-label="Toggle navigation"
      >
        <span class="sr-only">Toggle navigation</span>
        <svg v-if="!isMenuOpen" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-5 w-5">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-5 w-5">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="m6 6 12 12M6 18 18 6" />
        </svg>
      </button>

      <div class="hidden items-center gap-8 text-sm md:flex">
        <a
          v-for="item in props.navigation"
          :key="item.label"
          :href="item.href"
          class="text-slate-300 transition hover:text-white"
        >
          {{ item.label }}
        </a>
        <a
          href="#contact"
          class="rounded-full border border-cyan-500/60 bg-cyan-500/10 px-4 py-2 font-medium text-cyan-200 transition hover:-translate-y-0.5 hover:border-cyan-400 hover:bg-cyan-400/20 hover:text-white"
        >
          Let’s work together
        </a>
      </div>
    </nav>

    <transition name="fade">
      <div v-if="isMenuOpen" class="md:hidden">
        <div class="mx-6 mb-4 rounded-2xl border border-white/10 bg-white/5 backdrop-blur-lg">
          <div class="flex flex-col divide-y divide-white/5">
            <a
              v-for="item in props.navigation"
              :key="`mobile-${item.label}`"
              :href="item.href"
              class="px-5 py-4 text-sm text-slate-200 transition hover:bg-white/5"
              @click="closeMenu"
            >
              {{ item.label }}
            </a>
            <a
              href="#contact"
              class="px-5 py-4 text-sm font-medium text-cyan-200 transition hover:bg-cyan-500/10"
              @click="closeMenu"
            >
              Let’s work together
            </a>
          </div>
        </div>
      </div>
    </transition>
  </header>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 180ms ease, transform 180ms ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-6px);
}
</style>
