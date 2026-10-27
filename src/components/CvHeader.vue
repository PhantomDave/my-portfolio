<script setup lang="ts">
export type ContactLink = {
  label: string
  href: string
}

defineProps<{ contacts: ContactLink[] }>()
</script>

<template>
  <header class="border-b-2 border-accent pb-6">
    <div class="flex flex-wrap items-start justify-between gap-x-8 gap-y-4">
      <div>
        <h1 class="text-[2.5rem] font-bold leading-none tracking-[-0.015em]">Davide Rodo</h1>
        <p class="mt-2 text-lg font-medium text-accent">Software engineer</p>
      </div>
      <a
        href="/Davide_Rodo_CV.pdf"
        download
        class="inline-flex items-center gap-2 border border-accent px-4 py-2 text-[0.9375rem] font-medium text-accent hover:bg-accent hover:text-sheet print:hidden"
      >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" class="h-4 w-4" aria-hidden="true">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.8" d="M12 4v11m0 0 4-4m-4 4-4-4M5 19h14" />
        </svg>
        Download PDF
      </a>
    </div>

    <ul class="mt-5 flex flex-wrap gap-x-6 gap-y-1 text-[0.9375rem] text-ink-muted">
      <li>Catania, Italy</li>
      <li v-for="contact in contacts" :key="contact.href">
        <a
          :href="contact.href"
          class="underline decoration-accent/40 hover:text-accent hover:decoration-current"
          v-bind="contact.href.startsWith('http') ? { target: '_blank', rel: 'noreferrer' } : {}"
        >
          {{ contact.label }}
        </a>
      </li>
    </ul>
  </header>
</template>
