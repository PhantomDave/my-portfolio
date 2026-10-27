<script setup lang="ts">
export type EducationEntry = {
  year: string
  title: string
  place: string
}

defineProps<{ education: EducationEntry[] }>()
</script>

<template>
  <section aria-labelledby="education-heading">
    <h2 id="education-heading" class="border-b border-rule pb-1.5 text-[1.0625rem] font-semibold text-accent">
      Education
    </h2>

    <ul class="mt-4 space-y-3">
      <li v-for="entry in education" :key="entry.title">
        <p class="text-[0.875rem] font-semibold tabular-nums text-accent">{{ entry.year }}</p>
        <p class="font-semibold leading-snug">{{ entry.title }}</p>
        <p class="text-[0.9375rem] text-ink-muted">{{ entry.place }}</p>
      </li>
    </ul>
  </section>
</template>
