# Davide Rodo — Portfolio

Personal site built with [Vue 3](https://vuejs.org/), [TypeScript](https://www.typescriptlang.org/), [Vite](https://vite.dev/), and the experimental [Tailwind CSS v4](https://tailwindcss.com/blog/tailwindcss-v4-alpha). It mirrors the structure of boutique studio portfolios, focusing on crisp storytelling, services, and measurable impact.

## Local development

```fish
npm install
npm run dev
```

## Production build

```fish
npm run build
```

## Architecture

- `src/style.css` — global theme (fonts, background gradients, utility helpers)
- `src/App.vue` — data-driven layout wiring the page sections
- `src/components` — modular sections for hero, services, experience, projects, and contact CTA

## Customisation

- Update navigation labels, social links, and project data inside `src/App.vue`
- Replace placeholder imagery in `HeroSection.vue` and project cards with real assets or media embeds
- Point CTA links to your actual resume, calendar, and live case studies

## License

MIT — use, remix, and ship.
