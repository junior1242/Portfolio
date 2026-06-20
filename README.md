# Shahid Ali — Portfolio (Vue 3 + Vite)

A modern, responsive personal portfolio built with **Vue 3**, **Vite**, and **Tailwind CSS**. It features a full-page layout with smooth navigation, animated sections, and a mailto-based contact form.

## Live Sections

- **Hero** (profile image, headline, primary CTAs)
- **About** (experience & details cards)
- **Skills** (categorized expertise + tags)
- **Projects** (featured project cards with links)
- **Contact** (name/email/message form; opens `mailto:` with a prefilled subject/body)
- **Footer**

## Tech Stack

- Vue 3 (Composition API)
- Vite
- Tailwind CSS (via `@tailwindcss/vite`)
- ESLint + Prettier

## Project Structure

- `src/App.vue` – page layout that composes all sections
- `src/components/` – UI sections (NavBar, Hero, About, Skills, Projects, Contact, Footer)
- `src/assets/` – images and shared styles
- `src/assets/main.css` – global styling (gradients, buttons, cards, helpers)

## Getting Started

### 1) Install dependencies

```sh
npm install
```

### 2) Run development server

```sh
npm run dev
```

### 3) Build for production

```sh
npm run build
```

### 4) Preview production build

```sh
npm run preview
```

## Linting & Formatting

```sh
npm run lint
npm run format
```

## Notes

- The **contact form** uses a client-side `mailto:` link generated in `src/components/ContactSection.vue`.
- The navigation links point to section IDs: `#about`, `#skills`, `#projects`, `#contact`.

---

Built with 💜 by Shahid Ali.
