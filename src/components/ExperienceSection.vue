<script setup lang="ts">
export type Employer = {
  company: string
  place: string
  roles: {
    title: string
    period: string
    highlights: string[]
  }[]
}

defineProps<{ employers: Employer[] }>()
</script>

<template>
  <section aria-labelledby="experience-heading">
    <h2 id="experience-heading" class="border-b border-rule pb-1.5 text-[1.0625rem] font-semibold text-accent">
      Experience
    </h2>

    <div class="mt-5 space-y-8">
      <article v-for="employer in employers" :key="employer.company">
        <header class="flex flex-wrap items-baseline justify-between gap-x-4">
          <h3 class="text-xl font-semibold">{{ employer.company }}</h3>
          <p class="text-[0.9375rem] text-ink-muted">{{ employer.place }}</p>
        </header>

        <div
          v-for="role in employer.roles"
          :key="role.title"
          class="mt-3 border-l-2 border-rule pl-4"
        >
          <div class="flex flex-wrap items-baseline justify-between gap-x-4">
            <h4 class="font-semibold">{{ role.title }}</h4>
            <p class="text-[0.9375rem] tabular-nums text-ink-muted">{{ role.period }}</p>
          </div>
          <ul class="mt-1.5 list-disc space-y-1 pl-4 marker:text-accent">
            <li v-for="highlight in role.highlights" :key="highlight">{{ highlight }}</li>
          </ul>
        </div>
      </article>
    </div>
  </section>
</template>
