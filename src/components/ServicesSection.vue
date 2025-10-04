<script setup lang="ts">
export type Service = {
  title: string
  description: string
  bullets: string[]
}

defineProps<{ services: Service[] }>()
</script>

<template>
  <section aria-labelledby="services-heading" class="space-y-10">
    <div class="flex flex-col gap-4 sm:flex-row sm:items-end sm:justify-between">
      <div class="max-w-2xl space-y-3">
        <p class="text-sm uppercase tracking-[0.25em] text-cyan-300/70">Capabilities</p>
        <h2 id="services-heading" class="text-3xl font-semibold text-slate-50 sm:text-4xl">
          Partnering across product, design, and engineering to launch and scale experiences that matter.
        </h2>
      </div>
      <p class="max-w-sm text-sm text-slate-400">
        I slot into teams as an embedded lead or fractional partner—tight feedback loops, transparent metrics, and calm delivery.
      </p>
    </div>

    <div class="grid gap-6 md:grid-cols-3">
      <article
        v-for="service in services"
        :key="service.title"
        class="flex h-full flex-col rounded-3xl border border-white/10 bg-white/5 p-8 transition hover:border-cyan-400/60 hover:bg-cyan-400/10"
      >
        <div>
          <h3 class="text-xl font-semibold text-slate-50">{{ service.title }}</h3>
          <p class="mt-3 text-sm text-slate-400">{{ service.description }}</p>
        </div>
        <ul class="mt-6 space-y-3 text-sm text-slate-300">
          <li
            v-for="bullet in service.bullets"
            :key="bullet"
            class="flex items-start gap-3"
          >
            <span class="mt-1 h-2 w-2 flex-shrink-0 rounded-full bg-gradient-to-r from-sky-400 to-emerald-400" />
            <span>{{ bullet }}</span>
          </li>
        </ul>
      </article>
    </div>
  </section>
</template>
