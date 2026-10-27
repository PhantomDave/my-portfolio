# Davide Rodo — Portfolio

Personal site built with [Vue 3](https://vuejs.org/), [TypeScript](https://www.typescriptlang.org/), [Vite](https://vite.dev/), and the experimental [Tailwind CSS v4](https://tailwindcss.com/blog/tailwindcss-v4-alpha). The site is laid out as a single-page CV and shares its palette with the printable CV in `cv/`.

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

- `src/style.css` — theme tokens (light, dark and print)
- `src/App.vue` — CV content (experience, projects, skills, education) and the sheet layout
- `src/components` — header, experience, projects, expertise and education sections

## Customisation

- Update content inside `src/App.vue`, and keep `cv/cv.html` in sync when it changes

## License

MIT — use, remix, and ship.
