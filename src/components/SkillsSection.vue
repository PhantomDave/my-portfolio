<script setup lang="ts">
export type SkillGroup = {
  area: string
  tools: string[]
}

defineProps<{ skills: SkillGroup[] }>()
</script>

<template>
  <section aria-labelledby="skills-heading">
    <h2 id="skills-heading" class="border-b border-rule pb-1.5 text-[1.0625rem] font-semibold text-accent">
      Expertise
    </h2>

    <dl class="mt-4 space-y-3">
      <div v-for="group in skills" :key="group.area">
        <dt class="text-[0.875rem] font-semibold text-ink-muted">{{ group.area }}</dt>
        <dd>{{ group.tools.join(", ") }}</dd>
      </div>
    </dl>
  </section>
</template>
