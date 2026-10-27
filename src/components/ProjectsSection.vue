<script setup lang="ts">
export type Project = {
  name: string
  description: string
  stack: string[]
  href?: string
}

defineProps<{ projects: Project[] }>()
</script>

<template>
  <section aria-labelledby="projects-heading">
    <h2 id="projects-heading" class="border-b border-rule pb-1.5 text-[1.0625rem] font-semibold text-accent">
      Selected projects
    </h2>

    <ul class="mt-5 space-y-5">
      <li v-for="project in projects" :key="project.name">
        <h3 class="font-semibold">
          <a v-if="project.href" :href="project.href" class="underline decoration-accent/40 hover:text-accent hover:decoration-current">
            {{ project.name }}
          </a>
          <template v-else>{{ project.name }}</template>
        </h3>
        <p class="mt-0.5">{{ project.description }}</p>
        <p class="mt-1 text-[0.875rem] text-ink-muted">{{ project.stack.join(", ") }}</p>
      </li>
    </ul>
  </section>
</template>
