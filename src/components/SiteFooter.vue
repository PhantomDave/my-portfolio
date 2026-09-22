<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="border-t border-border bg-surface-000">
    <div class="mx-auto flex max-w-6xl flex-col gap-6 px-6 py-10 text-sm text-ink-faint sm:flex-row sm:items-center sm:justify-between sm:px-8 lg:px-12">
      <p class="text-ink-muted">© {{ currentYear }} Davide Rodo. Crafted with Vue & Tailwind.</p>
      <div class="flex flex-wrap items-center gap-4">
        <a href="#about" class="transition hover:text-ink">About</a>
        <a href="#experience" class="transition hover:text-ink">Experience</a>
        <a href="#work" class="transition hover:text-ink">Work</a>
        <a href="#contact" class="transition hover:text-ink">Contact</a>
      </div>
    </div>
  </footer>
</template>
