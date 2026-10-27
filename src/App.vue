<script setup lang="ts">
import CvHeader, { type ContactLink } from "./components/CvHeader.vue";
import ExperienceSection, {
  type Employer,
} from "./components/ExperienceSection.vue";
import ProjectsSection, {
  type Project,
} from "./components/ProjectsSection.vue";
import SkillsSection, { type SkillGroup } from "./components/SkillsSection.vue";
import EducationSection, {
  type EducationEntry,
} from "./components/EducationSection.vue";

const contacts: ContactLink[] = [
  { label: "davide.rodo@pdave.dev", href: "mailto:davide.rodo@pdave.dev" },
  { label: "github.com/PhantomDave", href: "https://github.com/PhantomDave" },
  {
    label: "LinkedIn",
    href: "https://www.linkedin.com/in/davide-rodo-23829419b/",
  },
];

const employers: Employer[] = [
  {
    company: "Bax Energy",
    place: "Acireale, Italy (hybrid)",
    roles: [
      {
        title: "R&D Software Engineer",
        period: "Apr 2024 – present",
        highlights: [
          "Develop full stack features in C# (.NET) and Next.js/React for an Asset Performance Management platform monitoring several GW of renewable energy assets across Europe and Asia",
          "Design and implement REST and SOAP APIs powering client-facing analytics and third-party integrations",
          "Provision and manage Azure and AWS infrastructure with Terraform, replacing manual setup with reproducible deployments",
          "Containerize services with Docker and orchestrate them on Kubernetes to standardize releases across environments",
          "Optimize services and database queries to improve platform responsiveness under production load",
          "Work in cross-functional Agile teams of ~6 engineers, scaling to roughly 50 contributors at peak on the platform's largest delivery cycle",
        ],
      },
      {
        title: "Software Engineer",
        period: "Jan 2024 – Mar 2024",
        highlights: [
          "Maintained and extended legacy components of the Asset Performance Management suite",
          "Built Microsoft Teams and GitHub integrations that automated notification and alarm handling, removing manual triage from the team's daily workflow",
          "Worked across Angular, Next.js and .NET Framework, integrating REST and SOAP services deployed on Azure and AWS",
        ],
      },
    ],
  },
  {
    company: "Voxel Entertainment ApS",
    place: "Remote",
    roles: [
      {
        title: "Software Engineer / Team Lead",
        period: "2019 – 2023",
        highlights: [
          "Led a development team of 4 engineers and managed a player community of approximately 1,000 users",
          "Developed complex multiplayer gamemodes in C# and JavaScript, including backend services and REST APIs",
          "Built websites and User Control Panels in PHP, both plain and on WordPress",
          "Migrated the codebase from .NET Framework to .NET Core and administered the Linux cloud servers running the platform",
        ],
      },
    ],
  },
];

const projects: Project[] = [
  {
    name: "Conductor",
    description:
      "Open-source universal task runner and real-time dashboard: starts a full dev stack from one declarative YAML file, with dependency-aware health checks and a desktop app.",
    stack: ["TypeScript", "Bun", "React", "Fastify", "SQLite", "Tauri"],
    href: "https://github.com/PhantomDave/conductor",
  },
  {
    name: "Gym Manager",
    description:
      "Desktop app for a small gym's front desk: memberships, health certificate expiry, and document storage. Built to run on 2GB of RAM, with zero network calls.",
    stack: ["Rust", "Tauri", "TypeScript", "Preact", "SQLite"],
    href: "https://github.com/PhantomDave/gym-manager",
  },
  {
    name: "Bank Tracker",
    description:
      "Full-stack personal finance tracker with a GraphQL API, configurable dashboards and widgets, CSV import, and Dockerized deployment behind Nginx.",
    stack: ["C#", ".NET", "GraphQL", "Angular", "PostgreSQL", "Docker"],
    href: "https://github.com/PhantomDave/BankTrackerGraphQL",
  },
  {
    name: "Proxmox Discord Connector",
    description:
      "Discord bot exposing Proxmox VE controls as slash commands, published to PyPI with a Docker image on GHCR.",
    stack: ["Python", "Discord API", "Proxmox", "Docker", "CI/CD"],
    href: "https://github.com/PhantomDave/proxmox-discord-connector",
  },
  {
    name: "Git Town VS Code Extension",
    description:
      "Wraps Git Town's branching workflow (sync, hack, ship, propose) in a sidebar UI and command palette. Published on the VS Code Marketplace.",
    stack: ["TypeScript", "VS Code API", "esbuild", "CI/CD"],
    href: "https://github.com/PhantomDave/git-town-vscode-extension",
  },
  {
    name: "South Valley Roleplay",
    description:
      "GTA V roleplay server: I engineered the gamemode end to end in C#, shaped the backend systems, and mentored contributors.",
    stack: ["C#", "SQL", "REST APIs", "Docker", "CI/CD", "Linux"],
  },
];

const skills: SkillGroup[] = [
  {
    area: "Languages",
    tools: [
      "C#",
      "TypeScript / JavaScript",
      "SQL",
      "PHP",
      "Python",
      "Rust",
      "Java",
      "C / C++",
    ],
  },
  {
    area: "Frameworks",
    tools: [".NET", "Next.js", "React", "Vue", "Angular", "Tauri"],
  },
  {
    area: "Cloud & DevOps",
    tools: [
      "Azure",
      "AWS",
      "Terraform",
      "Docker",
      "Kubernetes",
      "Git",
      "CI/CD",
    ],
  },
  {
    area: "AI engineering",
    tools: [
      "Claude Code",
      "GitHub Copilot",
      "OpenCode",
      "local LLMs (Ollama, LM Studio)",
      "agentic coding workflows",
    ],
  },
  {
    area: "Practices",
    tools: [
      "REST & SOAP API design",
      "Agile / Scrum",
      "legacy modernization",
      "code review & mentoring",
    ],
  },
  { area: "Systems", tools: ["Linux", "Windows"] },
];

const education: EducationEntry[] = [
  {
    year: "2023",
    title: "Full Stack Developer Course",
    place: "Free Mind Foundry, Acireale",
  },
  {
    year: "2017",
    title: "High School Diploma",
    place: "IPSSEOA “Karol Wojtyła”, Catania",
  },
];

const languages = [
  { name: "Italian", level: "Native" },
  { name: "English", level: "C1" },
];
</script>

<template>
  <div class="sm:px-6 print:px-0">
    <main
      class="mx-auto max-w-[62rem] bg-sheet px-6 py-10 sm:my-12 sm:px-12 sm:py-14 sm:shadow-[0_1px_2px_rgb(20_32_46/0.06),0_12px_32px_-12px_rgb(20_32_46/0.18)] print:my-0 print:max-w-none print:p-0 print:shadow-none"
    >
      <CvHeader :contacts="contacts" />

      <p class="mt-6 max-w-[44rem] text-[1.0625rem]">
        Full-stack engineer working mostly in .NET and Next.js/React. I build
        monitoring software for the renewable energy sector, currently an Asset
        Performance Management platform covering several GW of assets across
        Europe and Asia, and I look after the cloud side too: Azure and AWS with
        Terraform, Docker and Kubernetes. Before that I led a small team and
        moved a game platform from .NET Framework to .NET Core. I use AI coding
        agents and local LLMs every day. Open to full-stack roles.
      </p>

      <div
        class="mt-10 grid gap-x-12 gap-y-10 md:grid-cols-[1fr_15rem] print:grid-cols-[1fr_13rem]"
      >
        <div class="min-w-0 space-y-10">
          <ExperienceSection :employers="employers" />
          <ProjectsSection :projects="projects" />
        </div>

        <aside class="space-y-10">
          <SkillsSection :skills="skills" />
          <EducationSection :education="education" />

          <section aria-labelledby="languages-heading">
            <h2
              id="languages-heading"
              class="border-b border-rule pb-1.5 text-[1.0625rem] font-semibold text-accent"
            >
              Languages
            </h2>
            <dl class="mt-4 space-y-1">
              <div
                v-for="language in languages"
                :key="language.name"
                class="flex justify-between gap-4"
              >
                <dt class="font-semibold">{{ language.name }}</dt>
                <dd class="text-ink-muted">{{ language.level }}</dd>
              </div>
            </dl>
          </section>
        </aside>
      </div>
    </main>
  </div>
</template>
