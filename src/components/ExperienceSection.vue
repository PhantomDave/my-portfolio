<script setup lang="ts">
export type ExperienceEntry = {
  company: string
  role: string
  period: string
  summary: string
  highlights: string[]
}

defineProps<{ experience: ExperienceEntry[] }>()
</script>

<template>
  <section aria-labelledby="experience-heading" class="space-y-12">
    <div class="max-w-2xl space-y-3">
      <p class="font-mono text-xs uppercase tracking-[0.25em] text-ink-muted">Experience</p>
      <h2 id="experience-heading" class="text-3xl font-semibold text-ink sm:text-4xl">
        Leadership rooted in craft—shaping strategy while still hands-on with the code.
      </h2>
      <p class="text-sm text-ink-muted">
        Every engagement blends product thinking, tight execution, and enablement. Here’s the highlight reel.
      </p>
    </div>

    <div class="relative">
      <div class="absolute inset-y-0 left-4 hidden w-px bg-border md:block" />
      <div class="space-y-10">
        <article
          v-for="item in experience"
          :key="`${item.company}-${item.role}`"
          class="relative border border-border bg-surface-100 p-6 shadow-panel md:ml-12 md:pl-16"
        >
          <div class="absolute left-0 top-7 hidden h-3 w-3 -translate-x-1/2 border border-border-strong bg-accent shadow-[0_0_0_6px_var(--color-surface-100)] md:block" />
          <div class="flex flex-wrap items-center gap-3 text-sm text-ink-muted">
            <span class="rounded-xs bg-surface-accent-muted px-3 py-1 font-mono text-xs uppercase tracking-wider text-ink">
              {{ item.period }}
            </span>
            <span class="text-ink-faint">@</span>
            <span class="text-ink-muted">{{ item.company }}</span>
          </div>
          <h3 class="mt-4 text-2xl font-semibold text-ink">{{ item.role }}</h3>
          <p class="mt-3 text-sm text-ink-muted">{{ item.summary }}</p>
          <ul class="mt-5 space-y-3 text-sm text-ink-muted">
            <li
              v-for="highlight in item.highlights"
              :key="highlight"
              class="flex items-start gap-3"
            >
              <span class="mt-1.5 h-1.5 w-1.5 flex-shrink-0 bg-accent" />
              <span>{{ highlight }}</span>
            </li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>
