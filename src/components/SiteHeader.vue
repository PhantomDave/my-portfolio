<script setup lang="ts">
import { ref } from 'vue'

type NavigationItem = {
  label: string
  href: string
}

const props = defineProps<{ navigation: NavigationItem[] }>()

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <header class="fixed inset-x-0 top-0 z-40 border-b border-border bg-surface-100">
    <nav class="mx-auto flex max-w-6xl items-center justify-between gap-6 px-6 py-5 text-sm sm:px-8 lg:px-12">
      <a href="#top" class="group flex items-center gap-3 font-medium tracking-tight">
        <span class="relative text-lg text-ink">
          Davide Rodo
          <span class="absolute -bottom-1 left-0 h-[2px] w-full scale-x-0 bg-accent transition-transform duration-300 group-hover:scale-x-100" />
        </span>
        <span class="hidden rounded-xs bg-surface-accent-muted px-3 py-1 font-mono text-xs uppercase tracking-[0.08em] text-ink sm:inline-flex">Portfolio 2026</span>
      </a>

      <button
        class="relative inline-flex h-9 w-9 items-center justify-center border border-border bg-surface-100 text-ink outline-none transition hover:border-border-strong focus-visible:ring focus-visible:ring-accent md:hidden"
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
          class="text-ink-muted transition hover:text-ink"
        >
          {{ item.label }}
        </a>
        <a
          href="/Davide_Rodo_CV.pdf"
          download
          class="text-ink-muted transition hover:text-ink"
        >
          CV
        </a>
        <a
          href="#contact"
          class="bg-accent px-4 py-2 font-medium text-on-accent shadow-panel transition hover:-translate-y-0.5"
        >
          Let’s work together
        </a>
      </div>
    </nav>

    <transition name="fade">
      <div v-if="isMenuOpen" class="md:hidden">
        <div class="mx-6 mb-4 border border-border bg-surface-100">
          <div class="flex flex-col divide-y divide-border">
            <a
              v-for="item in props.navigation"
              :key="`mobile-${item.label}`"
              :href="item.href"
              class="px-5 py-4 text-sm text-ink transition hover:bg-surface-200"
              @click="closeMenu"
            >
              {{ item.label }}
            </a>
            <a
              href="/Davide_Rodo_CV.pdf"
              download
              class="px-5 py-4 text-sm text-ink transition hover:bg-surface-200"
              @click="closeMenu"
            >
              Download CV
            </a>
            <a
              href="#contact"
              class="px-5 py-4 text-sm font-medium text-accent transition hover:bg-surface-200"
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
