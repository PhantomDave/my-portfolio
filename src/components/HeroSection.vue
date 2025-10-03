<script setup lang="ts">
type SocialLink = {
  label: string
  href: string
}

defineProps<{ socials: SocialLink[] }>()
</script>

<template>
  <section class="grid gap-12 lg:grid-cols-[1.6fr,1fr] lg:items-end">
    <div class="space-y-10">
      <div class="inline-flex items-center gap-3 rounded-full border border-white/10 bg-white/5 px-4 py-2 text-xs uppercase tracking-[0.2em] text-cyan-200">
        <span class="h-2 w-2 rounded-full bg-cyan-400" />
        Open for senior front-end leadership roles
      </div>

      <div class="space-y-6">
        <h1 class="text-balance text-4xl font-semibold tracking-tight text-slate-50 sm:text-5xl md:text-6xl">
          I design and build products that feel effortless—even when the systems underneath are anything but.
        </h1>
        <p class="text-pretty text-lg text-slate-300 sm:text-xl">
          I’m Dave, a developer obsessed with crafted interfaces, sustainable architecture, and teams that ship with confidence. I partner with founders and product orgs to translate bold ideas into resilient, measurable software.
        </p>
      </div>

      <div class="flex flex-wrap gap-4">
        <a
          href="#work"
          class="inline-flex items-center gap-2 rounded-full bg-gradient-to-r from-sky-400 via-cyan-400 to-emerald-400 px-6 py-3 text-sm font-semibold text-slate-950 shadow-lg shadow-cyan-500/30 transition hover:-translate-y-0.5"
        >
          See recent work
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" class="h-4 w-4">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.6" d="m8.5 5.5 7 7-7 7" />
          </svg>
        </a>
        <a
          href="mailto:hello@pdave.dev"
          class="inline-flex items-center gap-2 rounded-full border border-white/15 bg-white/5 px-6 py-3 text-sm font-semibold text-slate-100 transition hover:border-white/30 hover:bg-white/10"
        >
          Request a proposal
        </a>
      </div>

      <ul class="grid gap-6 sm:grid-cols-3">
        <li class="rounded-2xl border border-white/10 bg-white/5 px-5 py-6">
          <p class="text-3xl font-semibold text-slate-50">12+</p>
          <p class="mt-1 text-sm text-slate-400">Years shipping digital products</p>
        </li>
        <li class="rounded-2xl border border-white/10 bg-white/5 px-5 py-6">
          <p class="text-3xl font-semibold text-slate-50">45%</p>
          <p class="mt-1 text-sm text-slate-400">Average performance gains per engagement</p>
        </li>
        <li class="rounded-2xl border border-white/10 bg-white/5 px-5 py-6">
          <p class="text-3xl font-semibold text-slate-50">30k+</p>
          <p class="mt-1 text-sm text-slate-400">Users supported across platforms</p>
        </li>
      </ul>

      <div class="flex flex-wrap items-center gap-4 text-sm text-slate-400">
        <span class="font-medium tracking-wide text-slate-200">Find me online</span>
        <span class="h-px w-12 bg-white/10" />
        <a
          v-for="social in socials"
          :key="social.label"
          :href="social.href"
          class="transition hover:text-white"
          target="_blank"
          rel="noreferrer"
        >
          {{ social.label }}
        </a>
      </div>
    </div>

    <aside class="group relative flex h-full items-end justify-center">
      <div class="relative w-full max-w-xs rounded-[32px] border border-white/10 bg-gradient-to-br from-white/10 via-white/5 to-transparent p-1 shadow-[0_15px_60px_rgba(15,118,230,0.28)]">
        <div class="relative overflow-hidden rounded-[28px] border border-white/15 bg-slate-900/80 px-8 pb-10 pt-16 text-center">
          <div class="absolute -top-6 left-1/2 h-24 w-24 -translate-x-1/2 rounded-2xl bg-gradient-to-br from-cyan-400 via-sky-500 to-emerald-400 opacity-90 blur-2xl transition group-hover:opacity-100" />
          <div class="relative mx-auto mb-6 h-28 w-28 rounded-2xl border border-white/20 bg-gradient-to-br from-slate-700 via-slate-800 to-slate-900 shadow-lg" />
          <h2 class="relative text-lg font-semibold text-slate-50">Davide Rodo</h2>
          <p class="relative mt-2 text-sm text-slate-400">Senior Front-End Engineer & UX Partner</p>
          <div class="relative mt-6 space-y-3 text-left text-xs text-slate-400">
            <div class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-emerald-400" />
              Leading multidisciplinary squads
            </div>
            <div class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-sky-400" />
              Mentoring engineers & designers
            </div>
            <div class="flex items-center gap-3">
              <span class="h-2 w-2 rounded-full bg-indigo-400" />
              Building measurable product outcomes
            </div>
          </div>
        </div>
      </div>
    </aside>
  </section>
</template>
