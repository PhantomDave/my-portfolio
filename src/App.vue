<script setup lang="ts">
import SiteHeader from "./components/SiteHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import ServicesSection from "./components/ServicesSection.vue";
import ExperienceSection from "./components/ExperienceSection.vue";
import EducationSection from "./components/EducationSection.vue";
import ProjectsSection, { type Project } from "./components/ProjectsSection.vue";
import ContactSection from "./components/ContactSection.vue";
import SiteFooter from "./components/SiteFooter.vue";

type NavigationItem = {
  label: string;
  href: string;
};

type SocialLink = {
  label: string;
  href: string;
};

type Service = {
  title: string;
  description: string;
  bullets: string[];
};

type ExperienceEntry = {
  company: string;
  role: string;
  period: string;
  summary: string;
  highlights: string[];
};

type EducationEntry = {
  institution: string;
  credential: string;
  period: string;
  location: string;
  summary: string;
  highlights: string[];
};

const navigation: NavigationItem[] = [
  { label: "About", href: "#about" },
  { label: "Experience", href: "#experience" },
  // { label: "Education", href: "#education" },
  { label: "Work", href: "#work" },
  { label: "Contact", href: "#contact" },
];

const socials: SocialLink[] = [
  { label: "LinkedIn", href: "https://www.linkedin.com/in/davide-rodo-23829419b/" },
  { label: "GitHub", href: "https://github.com/PhantomDave" },
];

const services: Service[] = [
  {
    title: "Full-Stack Development",
    description:
      "From database design to pixel-perfect UIs, I build complete solutions that scale across the entire stack.",
    bullets: [
      "RESTful APIs and database architecture",
      "Modern frontend frameworks (Vue, Angular, React)",
      "Cloud deployment and DevOps automation",
    ],
  },
  {
    title: "Backend Engineering",
    description:
      "I architect robust server-side systems using C#, .NET, PHP, and Python to power modern applications.",
    bullets: [
      "Microservices and distributed system design",
      "Database optimization and performance tuning",
      "API design and integration patterns",
    ],
  },
  {
    title: "Team Leadership & Mentorship",
    description:
      "I guide development teams through complex technical challenges while fostering a collaborative engineering culture.",
    bullets: [
      "Code review and architecture guidance",
      "Agile methodologies and project coordination",
      "Junior developer mentorship and onboarding",
    ],
  },
];

const experience: ExperienceEntry[] = [
  {
    company: "BaxEnergy",
    role: "Software Engineer",
    period: "Jan 2025 – Present · 10 mos",
    summary:
      "Supporting BaxEnergy’s energy platform from Acireale (Hybrid), pairing with senior engineers to deliver .NET features and web enhancements.",
    highlights: [
      "Prototype and ship .NET features across core web engineering initiatives",
      "Shadow senior teammates to harden delivery pipelines and review production code",
      "Assist with customer-facing demos and documentation for new energy modules",
    ],
  },
  {
    company: "BaxEnergy",
    role: "Software Developer",
    period: "Jan 2024 – Dec 2024 · 1 yr",
    summary:
      "Delivered C# and PHP solutions for BaxEnergy clients, balancing feature work with platform modernization efforts.",
    highlights: [
      "Implemented .NET services and integrations that underpin energy analytics workloads",
      "Maintained and refactored PHP components while trimming legacy technical debt",
      "Coordinated with designers and PMs to launch monitoring dashboards to production",
    ],
  },
  {
    company: "Voxel Entertainment APS",
    role: "Software Engineer · Part-time",
    period: "Jan 2020 – Jun 2023 · 3 yrs 6 mos",
    summary:
      "Remote contributor ensuring the studio’s Linux infrastructure and backend tooling stayed resilient for the game teams.",
    highlights: [
      "Managed and maintained Linux virtual machines powering production services",
      "Led and coordinated a distributed C# development team to deliver features on schedule",
      "Built deployment tooling that reduced release incidents and improved observability",
    ],
  },
];

const education: EducationEntry[] = [
  {
    institution: "IPSSEOA Istituto Alberghiero Karol Wojtyla Catania",
    credential:
      "Diploma Istituto Tecnico e Professionale · Servizio di ristorazione, cameriere/cameriera e responsabile di sala",
    period: "2012 – 2017",
    location: "Catania, Italy",
    summary:
      "Five-year program focused on hospitality operations, people management, and customer experience.",
    highlights: [
      "Leadership training in front-of-house team coordination and service standards",
      "Hands-on coursework in menu design, event planning, and guest satisfaction metrics",
      "Graduated with a final grade of 70/100",
      "Contributed to school-led hospitality showcases and community events",
    ],
  },
];

const projects: Project[] = [
  {
    name: "South Valley Roleplay",
    description:
      "A Grand Theft Auto V roleplay server launched on a new platform; I engineered the gamemode end to end in C#, shaped backend systems, and mentored contributors.",
    stack: [
      "C#",
      "SQL",
      "OOP",
      "Game Scripting",
      "Team Coordination",
      "Rest APIs",
      "SysAdmin",
      "Docker",
      "CI/CD",
      "Agile Methodologies",
    ],
    accent: "from-sky-400 via-cyan-500 to-emerald-400",
  },
  {
    name: "Money Tracker",
    description:
      "Lightweight finance companion built with a Python backend and Angular UI to keep daily expenses in check while traveling.",
    stack: ["Python", "Angular", "REST APIs"],
    linkLabel: "View project",
    linkHref: "https://github.com/PhantomDave/wheremoney",
    accent: "from-amber-400 via-orange-500 to-rose-400",
  },
];
</script>

<template>
  <div id="top" class="min-h-screen bg-slate-950 text-slate-100">
    <SiteHeader :navigation="navigation" />
    <main
      class="mx-auto flex max-w-6xl flex-col gap-28 px-6 pb-32 pt-32 sm:px-8 lg:px-12"
    >
      <HeroSection id="about" :socials="socials" />
      <ServicesSection :services="services" />
      <ExperienceSection id="experience" :experience="experience" />
      <!-- <EducationSection id="education" :education="education" /> -->
      <ProjectsSection id="work" :projects="projects" />
      <ContactSection id="contact" />
    </main>
    <SiteFooter />
  </div>
</template>
