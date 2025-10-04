<script setup lang="ts">
type EducationEntry = {
  institution: string
  credential: string
  period: string
  location: string
  summary: string
  highlights: string[]
}

defineProps<{ education: EducationEntry[] }>()
</script>

<template>
  <section aria-labelledby="education-heading" class="space-y-12">
    <div class="max-w-2xl space-y-3">
      <p class="text-sm uppercase tracking-[0.25em] text-cyan-300/70">Education</p>
      <h2 id="education-heading" class="text-3xl font-semibold text-slate-50 sm:text-4xl">
        Foundations in hospitality studies that seeded a love for structured systems and teamwork.
      </h2>
      <p class="text-sm text-slate-400">
        Coursework blended service leadership with the process discipline that now shapes my engineering craft.
      </p>
    </div>

    <div class="space-y-8">
      <article
        v-for="entry in education"
        :key="`${entry.institution}-${entry.credential}`"
        class="rounded-3xl border border-white/10 bg-white/5 p-6 md:flex md:items-start md:gap-10 md:p-8"
      >
        <header class="md:w-1/3">
          <p class="text-xs uppercase tracking-[0.3em] text-cyan-200">{{ entry.period }}</p>
          <h3 class="mt-3 text-xl font-semibold text-slate-50">{{ entry.institution }}</h3>
          <p class="mt-2 text-sm text-slate-400">{{ entry.location }}</p>
        </header>
        <div class="mt-6 space-y-4 text-sm text-slate-300 md:mt-0 md:flex-1">
          <p class="font-medium text-slate-200">{{ entry.credential }}</p>
          <p class="text-slate-400">{{ entry.summary }}</p>
          <ul class="space-y-2">
            <li
              v-for="highlight in entry.highlights"
              :key="highlight"
              class="flex items-start gap-3"
            >
              <span class="mt-1 h-2 w-2 flex-shrink-0 rounded-full bg-cyan-300" />
              <span>{{ highlight }}</span>
            </li>
          </ul>
        </div>
      </article>
    </div>
  </section>
</template>
