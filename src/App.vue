<script setup lang="ts">
import SiteHeader from "./components/SiteHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import ServicesSection, { type Service } from "./components/ServicesSection.vue";
import ExperienceSection, { type ExperienceEntry } from "./components/ExperienceSection.vue";
// import EducationSection from "./components/EducationSection.vue";
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

// type EducationEntry = {
//   institution: string;
//   credential: string;
//   period: string;
//   location: string;
//   summary: string;
//   highlights: string[];
// };

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

const resumeUrl = "/Davide_Rodo_CV.pdf";

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
    company: "Bax Energy",
    role: "R&D Software Engineer",
    period: "Apr 2024 – Present",
    summary:
      "Full stack engineering on an Asset Performance Management platform monitoring several GW of renewable energy assets across Europe and Asia, from Acireale (hybrid).",
    highlights: [
      "Develop full stack features in C# (.NET) and Next.js/React for the core monitoring platform",
      "Design and implement REST and SOAP APIs powering client-facing analytics and third-party integrations",
      "Provision and manage Azure and AWS infrastructure with Terraform, replacing manual setup with reproducible deployments",
      "Containerize services with Docker and orchestrate them on Kubernetes to standardize releases across environments",
      "Optimize services and database queries to improve platform responsiveness under production load",
      "Work in cross-functional Agile teams of ~6 engineers, scaling to roughly 50 contributors at peak on the platform's largest delivery cycle",
    ],
  },
  {
    company: "Bax Energy",
    role: "Software Engineer",
    period: "Jan 2024 – Mar 2024",
    summary:
      "Maintained and modernized legacy products in the Asset Performance Management suite for renewable energy operators.",
    highlights: [
      "Maintained and extended legacy APM components serving renewable energy operators",
      "Built Microsoft Teams and GitHub integrations that automated notification and alarm handling, removing manual triage from the team's daily workflow",
      "Worked across Angular, Next.js and .NET Framework, integrating REST and SOAP services deployed on Azure and AWS",
    ],
  },
  {
    company: "Voxel Entertainment ApS",
    role: "Software Engineer / Team Lead",
    period: "2019 – 2023",
    summary:
      "Remote technical lead for a multiplayer game platform, owning both the backend codebase and the Linux infrastructure behind it.",
    highlights: [
      "Led a development team of 4 engineers and managed a player community of approximately 1,000 users",
      "Developed complex multiplayer gamemodes in C# and JavaScript, including backend services and REST APIs",
      "Built websites and User Control Panels in PHP, both plain and on WordPress",
      "Migrated the codebase from .NET Framework to .NET Core and administered the Linux cloud servers running the platform",
    ],
  },
];

// const education: EducationEntry[] = [
//   {
//     institution: "IPSSEOA Istituto Alberghiero Karol Wojtyla Catania",
//     credential:
//       "Diploma Istituto Tecnico e Professionale · Servizio di ristorazione, cameriere/cameriera e responsabile di sala",
//     period: "2012 – 2017",
//     location: "Catania, Italy",
//     summary:
//       "Five-year program focused on hospitality operations, people management, and customer experience.",
//     highlights: [
//       "Leadership training in front-of-house team coordination and service standards",
//       "Hands-on coursework in menu design, event planning, and guest satisfaction metrics",
//       "Graduated with a final grade of 70/100",
//       "Contributed to school-led hospitality showcases and community events",
//     ],
//   },
// ];

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
      <HeroSection id="about" :socials="socials" :resume-url="resumeUrl" />
      <ServicesSection :services="services" />
      <ExperienceSection id="experience" :experience="experience" />
      <!-- <EducationSection id="education" :education="education" /> -->
      <ProjectsSection id="work" :projects="projects" />
      <ContactSection id="contact" />
    </main>
    <SiteFooter />
  </div>
</template>
