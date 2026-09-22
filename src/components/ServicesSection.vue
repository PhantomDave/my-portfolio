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
        <p class="font-mono text-xs uppercase tracking-[0.25em] text-ink-muted">Capabilities</p>
        <h2 id="services-heading" class="text-3xl font-semibold text-ink sm:text-4xl">
          Partnering across product, design, and engineering to launch and scale experiences that matter.
        </h2>
      </div>
      <p class="max-w-sm text-sm text-ink-muted">
        I slot into teams as an embedded lead or fractional partner—tight feedback loops, transparent metrics, and calm delivery.
      </p>
    </div>

    <div class="grid gap-6 md:grid-cols-3">
      <article
        v-for="service in services"
        :key="service.title"
        class="flex h-full flex-col border border-border bg-surface-100 p-8 shadow-panel transition hover:border-border-strong"
      >
        <div>
          <h3 class="text-xl font-semibold text-ink">{{ service.title }}</h3>
          <p class="mt-3 text-sm text-ink-muted">{{ service.description }}</p>
        </div>
        <ul class="mt-6 space-y-3 text-sm text-ink-muted">
          <li
            v-for="bullet in service.bullets"
            :key="bullet"
            class="flex items-start gap-3"
          >
            <span class="mt-1.5 h-1.5 w-1.5 flex-shrink-0 bg-accent" />
            <span>{{ bullet }}</span>
          </li>
        </ul>
      </article>
    </div>
  </section>
</template>
