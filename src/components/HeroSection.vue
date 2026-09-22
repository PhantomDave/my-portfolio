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
      <div class="inline-flex items-center gap-3 rounded-xs bg-surface-accent-muted px-4 py-2 font-mono text-xs uppercase tracking-[0.2em] text-ink">
        <span class="h-2 w-2 flex-shrink-0 rounded-full bg-signal-good" />
        Open for full-stack developer opportunities
      </div>

      <div class="space-y-6">
        <h1 class="text-balance text-4xl font-semibold tracking-tight text-ink sm:text-5xl md:text-6xl">
          I build full-stack solutions that scale—from robust backends to polished interfaces.
        </h1>
        <p class="text-pretty text-lg text-ink-muted sm:text-xl">
          I'm Davide, a full-stack engineer specializing in C#/.NET and Next.js/React. I build monitoring platforms for the renewable energy sector, automate the cloud infrastructure behind them, and have led a small team through a legacy-to-modern migration.
         </p>
      </div>

      <div class="flex flex-wrap gap-4">
        <a
          href="#work"
          class="inline-flex items-center gap-2 bg-accent px-6 py-3 text-sm font-semibold text-on-accent shadow-panel transition hover:-translate-y-0.5"
        >
          See recent work
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" class="h-4 w-4">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.6" d="m8.5 5.5 7 7-7 7" />
          </svg>
        </a>
        <a
          href="/Davide_Rodo_CV.pdf"
          download
          class="inline-flex items-center gap-2 border border-border bg-surface-100 px-6 py-3 text-sm font-semibold text-ink transition hover:border-border-strong"
        >
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" class="h-4 w-4">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.6" d="M12 4v11m0 0 4-4m-4 4-4-4M5 19h14" />
          </svg>
          Download CV
        </a>
        <a
          href="mailto:davide.rodo@pdave.dev"
          class="inline-flex items-center gap-2 border border-border bg-surface-100 px-6 py-3 text-sm font-semibold text-ink transition hover:border-border-strong"
        >
          Get in touch
        </a>
      </div>

      <ul class="grid gap-6 sm:grid-cols-3">
        <li class="border border-border bg-surface-100 px-5 py-6 shadow-panel">
          <p class="font-mono text-3xl font-semibold text-ink">6+</p>
          <p class="mt-1 text-sm text-ink-muted">Years building and shipping software</p>
        </li>
        <li class="border border-border bg-surface-100 px-5 py-6 shadow-panel">
          <p class="font-mono text-3xl font-semibold text-ink">Full-Stack</p>
          <p class="mt-1 text-sm text-ink-muted">C#, .NET, PHP, Python & Modern Frontend</p>
        </li>
        <li class="border border-border bg-surface-100 px-5 py-6 shadow-panel">
          <p class="font-mono text-3xl font-semibold text-ink">GW-scale</p>
          <p class="mt-1 text-sm text-ink-muted">Renewable assets monitored across Europe &amp; Asia</p>
        </li>
      </ul>

      <div class="flex flex-wrap items-center gap-4 text-sm text-ink-muted">
        <span class="font-medium tracking-wide text-ink">Find me online</span>
        <span class="h-px w-12 bg-border" />
        <a
          v-for="social in socials"
          :key="social.label"
          :href="social.href"
          class="transition hover:text-ink"
          target="_blank"
          rel="noreferrer"
        >
          {{ social.label }}
        </a>
      </div>
    </div>

    <aside class="relative flex h-full items-end justify-center">
      <div class="relative w-full max-w-xs border border-border bg-surface-100 p-1 shadow-panel">
        <div class="border border-border bg-surface-200 px-8 pb-10 pt-10 text-center">
          <div class="mx-auto mb-6 h-28 w-28 border border-border-strong bg-accent" />
          <h2 class="text-lg font-semibold text-ink">Davide Rodo</h2>
          <p class="mt-2 text-sm text-ink-muted">Full-Stack Engineer</p>
          <div class="mt-6 space-y-3 text-left text-xs text-ink-muted">
            <div class="flex items-center gap-3">
              <span class="h-1.5 w-1.5 flex-shrink-0 bg-accent" />
              Backend systems & APIs
            </div>
            <div class="flex items-center gap-3">
              <span class="h-1.5 w-1.5 flex-shrink-0 bg-accent" />
              Modern web frameworks
            </div>
            <div class="flex items-center gap-3">
              <span class="h-1.5 w-1.5 flex-shrink-0 bg-accent" />
              Team collaboration & mentoring
            </div>
          </div>
        </div>
      </div>
    </aside>
  </section>
</template>
