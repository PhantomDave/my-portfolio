<script setup lang="ts">
type Project = {
  name: string
  description: string
  stack: string[]
  linkLabel: string
  linkHref: string
  accent: string
}

defineProps<{ projects: Project[] }>()
</script>

<template>
  <section aria-labelledby="projects-heading" class="space-y-10">
    <div class="flex flex-col gap-3">
      <p class="text-sm uppercase tracking-[0.25em] text-cyan-300/70">Selected Work</p>
      <h2 id="projects-heading" class="text-3xl font-semibold text-slate-50 sm:text-4xl">
        High-impact case studies spanning product refactors, greenfield builds, and design system rollouts.
      </h2>
      <p class="max-w-3xl text-sm text-slate-400">
        Each project pairs craft with measurable outcomes—load times, activation rates, revenue, or team velocity. Ask me about the metrics that matter to you.
      </p>
    </div>

    <div class="grid gap-6 lg:grid-cols-3">
      <article
        v-for="project in projects"
        :key="project.name"
        class="group flex h-full flex-col overflow-hidden rounded-3xl border border-white/10 bg-white/5"
      >
        <div class="relative h-44 overflow-hidden">
          <div :class="['absolute inset-0 bg-gradient-to-r', project.accent]" />
          <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,_rgba(255,255,255,0.35),_transparent_60%)] opacity-50" />
          <div class="absolute bottom-4 left-4 flex items-center gap-3 text-xs font-medium uppercase tracking-[0.2em] text-slate-950">
            <span class="rounded-full bg-white/80 px-3 py-1">Case Study</span>
            <span class="rounded-full bg-white/60 px-3 py-1">{{ project.stack[0] }}</span>
          </div>
        </div>
        <div class="flex flex-1 flex-col gap-5 p-7">
          <header class="space-y-2">
            <h3 class="text-2xl font-semibold text-slate-50">{{ project.name }}</h3>
            <p class="text-sm text-slate-400">{{ project.description }}</p>
          </header>
          <ul class="flex flex-wrap gap-2 text-xs uppercase tracking-[0.2em] text-slate-300/70">
            <li
              v-for="tech in project.stack"
              :key="tech"
              class="rounded-full border border-white/10 bg-white/5 px-3 py-1"
            >
              {{ tech }}
            </li>
          </ul>
          <div class="mt-auto">
            <a
              :href="project.linkHref"
              class="inline-flex items-center gap-2 text-sm font-medium text-cyan-200 transition hover:text-white"
            >
              {{ project.linkLabel }}
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-4 w-4">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M5 12h14m0 0-6 6m6-6-6-6" />
              </svg>
            </a>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>
