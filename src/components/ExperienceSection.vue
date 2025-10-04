<script setup lang="ts">
type ExperienceEntry = {
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
      <p class="text-sm uppercase tracking-[0.25em] text-cyan-300/70">Experience</p>
      <h2 id="experience-heading" class="text-3xl font-semibold text-slate-50 sm:text-4xl">
        Leadership rooted in craft—shaping strategy while still hands-on with the code.
      </h2>
      <p class="text-sm text-slate-400">
        Every engagement blends product thinking, tight execution, and enablement. Here’s the highlight reel.
      </p>
    </div>

    <div class="relative">
      <div class="absolute inset-y-0 left-4 hidden w-px bg-gradient-to-b from-white/0 via-white/20 to-white/0 md:block" />
      <div class="space-y-10">
        <article
          v-for="item in experience"
          :key="`${item.company}-${item.role}`"
          class="relative rounded-3xl border border-white/10 bg-white/5 p-6 md:ml-12 md:pl-16"
        >
          <div class="absolute left-0 top-7 hidden h-3 w-3 -translate-x-1/2 rounded-full border border-white/30 bg-gradient-to-br from-sky-400 to-emerald-400 shadow-[0_0_0_6px_rgba(15,23,42,0.9)] md:block" />
          <div class="flex flex-wrap items-center gap-3 text-sm text-slate-400">
            <span class="rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs uppercase tracking-wider text-cyan-200">
              {{ item.period }}
            </span>
            <span class="text-slate-500">@</span>
            <span class="text-slate-300">{{ item.company }}</span>
          </div>
          <h3 class="mt-4 text-2xl font-semibold text-slate-50">{{ item.role }}</h3>
          <p class="mt-3 text-sm text-slate-400">{{ item.summary }}</p>
          <ul class="mt-5 space-y-3 text-sm text-slate-300">
            <li
              v-for="highlight in item.highlights"
              :key="highlight"
              class="flex items-start gap-3"
            >
              <span class="mt-1 h-2 w-2 flex-shrink-0 rounded-full bg-emerald-400" />
              <span>{{ highlight }}</span>
            </li>
          </ul>
        </article>
      </div>
    </div>
  </section>
</template>
