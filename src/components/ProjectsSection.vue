<script setup lang="ts">
export type Project = {
  name: string
  description: string
  stack: string[]
  linkLabel?: string
  linkHref?: string
}

defineProps<{ projects: Project[] }>()
</script>

<template>
  <section aria-labelledby="projects-heading" class="space-y-10">
    <div class="flex flex-col gap-3">
      <p class="font-mono text-xs uppercase tracking-[0.25em] text-ink-muted">Selected Work</p>
      <h2 id="projects-heading" class="text-3xl font-semibold text-ink sm:text-4xl">
        High-impact case studies spanning product refactors, greenfield builds, and design system rollouts.
      </h2>
      <p class="max-w-3xl text-sm text-ink-muted">
        Each project pairs craft with measurable outcomes—load times, activation rates, revenue, or team velocity. Ask me about the metrics that matter to you.
      </p>
    </div>

    <div class="grid gap-6 lg:grid-cols-3">
      <article
        v-for="project in projects"
        :key="project.name"
        class="flex h-full flex-col border border-border bg-surface-100 shadow-panel"
      >
        <div class="flex h-24 items-end border-b border-border bg-surface-200 p-3">
          <span class="font-mono text-xs uppercase tracking-[0.2em] text-ink-muted">{{ project.stack[0] }}</span>
        </div>
        <div class="flex flex-1 flex-col gap-5 p-7">
          <header class="space-y-2">
            <h3 class="text-2xl font-semibold text-ink">{{ project.name }}</h3>
            <p class="text-sm text-ink-muted">{{ project.description }}</p>
          </header>
          <ul class="flex flex-wrap gap-2 font-mono text-xs uppercase tracking-[0.2em] text-ink">
            <li
              v-for="tech in project.stack"
              :key="tech"
              class="rounded-xs bg-surface-accent-muted px-3 py-1"
            >
              {{ tech }}
            </li>
          </ul>
          <div v-if="project.linkLabel && project.linkHref" class="mt-auto">
            <a
              :href="project.linkHref"
              class="inline-flex items-center gap-2 text-sm font-medium text-accent transition hover:text-ink"
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
