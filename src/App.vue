<script setup lang="ts">
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import ServicesSection from './components/ServicesSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'

type NavigationItem = {
  label: string
  href: string
}

type SocialLink = {
  label: string
  href: string
}

type Service = {
  title: string
  description: string
  bullets: string[]
}

type ExperienceEntry = {
  company: string
  role: string
  period: string
  summary: string
  highlights: string[]
}

type Project = {
  name: string
  description: string
  stack: string[]
  linkLabel: string
  linkHref: string
  accent: string
}

const navigation: NavigationItem[] = [
  { label: 'About', href: '#about' },
  { label: 'Experience', href: '#experience' },
  { label: 'Work', href: '#work' },
  { label: 'Contact', href: '#contact' },
]

const socials: SocialLink[] = [
  { label: 'LinkedIn', href: 'https://www.linkedin.com/' },
  { label: 'GitHub', href: 'https://github.com/PhantomDave' },
  { label: 'X (Twitter)', href: 'https://x.com/' },
]

const services: Service[] = [
  {
    title: 'Product-Focused Engineering',
    description: 'From idea validation to polished releases, I ship experiences users actually love.',
    bullets: ['Lean product discovery workshops', 'Incremental delivery with measurable outcomes', 'Embedded analytics and A/B experimentation'],
  },
  {
    title: 'Frontend Architecture',
    description: 'I craft resilient, fast Vue stacks that scale with your roadmap instead of fighting it.',
    bullets: ['Design system foundations & tokens', 'SSR / SSG pipelines and CI tooling', 'Accessibility-first implementation'],
  },
  {
    title: 'Team Enablement',
    description: 'I grow teams through mentorship, solid docs, and guardrails that free engineers to move quickly.',
    bullets: ['Onboarding playbooks & pair programming', 'Automated quality gates and DX tooling', 'Knowledge sharing talks & workshops'],
  },
]

const experience: ExperienceEntry[] = [
  {
    company: 'Northwind Labs',
    role: 'Lead Frontend Engineer',
    period: '2022 — Present',
    summary: 'Scaled a design system across five product lines while reducing build times by 45%.',
    highlights: ['Directed a squad of 6 engineers and 2 designers', 'Introduced visual regression testing and release automation', 'Championed accessibility audits achieving WCAG 2.1 AA compliance'],
  },
  {
    company: 'Atlas Analytics',
    role: 'Senior Software Engineer',
    period: '2019 — 2022',
    summary: 'Modernized the customer intelligence platform with real-time dashboards consumed by 30k+ analysts.',
    highlights: ['Rolled out a modular micro-frontend architecture', 'Cut onboarding time from weeks to days with starter kits', 'Partnered with PMs to launch usage-based pricing experiments'],
  },
  {
    company: 'Freelance',
    role: 'Full-Stack Consultant',
    period: '2016 — 2019',
    summary: 'Helped early-stage startups validate ideas, land funding, and build their first engineering muscle.',
    highlights: ['Delivered MVPs for 12 funded startups', 'Implemented CI/CD pipelines from scratch', 'Coached founders on technical hiring and roadmapping'],
  },
]

const projects: Project[] = [
  {
    name: 'Pulseboard',
    description: 'A mission-critical ops dashboard with adaptive theming, live metrics, and granular permissions.',
    stack: ['Vue 3', 'TypeScript', 'Vite', 'WebSockets'],
    linkLabel: 'View case study',
    linkHref: '#',
    accent: 'from-sky-400 via-cyan-500 to-emerald-400',
  },
  {
    name: 'Forma UI',
    description: 'A component library powering complex forms, featuring auto-generated docs and accessibility baked in.',
    stack: ['Storybook', 'VueUse', 'Radix primitives'],
    linkLabel: 'Explore components',
    linkHref: '#',
    accent: 'from-violet-400 via-purple-500 to-fuchsia-400',
  },
  {
    name: 'Trailhead',
    description: 'A content platform for outdoor guides with long-form writing, geo search, and offline syncing.',
    stack: ['Nuxt', 'GraphQL', 'PostgreSQL', 'Cloudflare Workers'],
    linkLabel: 'See live product',
    linkHref: '#',
    accent: 'from-amber-400 via-orange-500 to-rose-400',
  },
]
</script>

<template>
  <div id="top" class="min-h-screen bg-slate-950 text-slate-100">
    <SiteHeader :navigation="navigation" />
    <main class="mx-auto flex max-w-6xl flex-col gap-28 px-6 pb-32 pt-32 sm:px-8 lg:px-12">
      <HeroSection id="about" :socials="socials" />
      <ServicesSection :services="services" />
      <ExperienceSection id="experience" :experience="experience" />
      <ProjectsSection id="work" :projects="projects" />
      <ContactSection id="contact" />
    </main>
    <SiteFooter />
  </div>
</template>
