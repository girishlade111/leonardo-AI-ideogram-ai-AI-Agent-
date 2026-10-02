# CharacterForge Imagix — AI Creation Platform UI

A pixel-rich, dark-themed homepage clone of an AI image-generation platform (in the style of Leonardo AI / Ideogram), generated with Lovable. It showcases the full landing experience of a modern AI creation suite: a prompt-first hero ("What would you like to create?"), creation cards, quick-start actions, featured apps, model cards, a sidebar navigation and a promo bar — all built with React, shadcn/ui and Tailwind CSS.

> This is a **front-end UI clone / concept demo**. The gallery images are bundled locally under `public/lovable-uploads/`; there is no backend and no AI API key required — it runs fully client-side.

## Features

- **Prompt-first hero** — "What would you like to create?" headline with creation cards for Image generation and Storytelling flows.
- **Quick starts grid** — Image-to-Video, canvas/paint tools and more, each with icon, label and "New" badges.
- **Featured apps & model cards** — cards showcasing AI models/apps with artwork from the bundled uploads.
- **Sidebar navigation + promo bar + header** — full app-shell layout with search and navigation.
- **Dark cinematic theme** — near-black surfaces (`#1A1A1A`), accent highlights, responsive grid layouts.
- **Client-side routing** — `react-router-dom` with a `NotFound` catch-all page.
- **shadcn/ui component library** — accordion, dialog, dropdown, toast, tooltip, sidebar, carousel primitives and more, wired with Radix UI + Tailwind.

## Tech Stack

| Layer      | Technology |
|------------|------------|
| Build      | Vite 5 |
| UI library | React 18 + TypeScript |
| Components | shadcn/ui (Radix UI primitives) |
| Styling    | Tailwind CSS 3 |
| Routing    | react-router-dom |
| Data       | TanStack React Query |
| Icons      | lucide-react |
| Generated with | [Lovable](https://lovable.dev) |

## Project Structure

```
├── index.html                 # HTML shell (title: characterforge-imagix)
├── public/
│   ├── favicon.ico / logo.svg / og-image.png
│   └── lovable-uploads/       # bundled gallery artwork (PNG)
├── src/
│   ├── main.tsx               # React root mount
│   ├── App.tsx                # providers + router (Index, NotFound)
│   ├── App.css / index.css    # global styles + Tailwind directives
│   ├── pages/
│   │   ├── Index.tsx          # homepage: hero, quick starts, featured, models
│   │   └── NotFound.tsx       # 404 catch-all
│   ├── components/
│   │   ├── Header.tsx / Sidebar.tsx / PromoBar.tsx
│   │   ├── CreationCard.tsx / QuickStartItem.tsx
│   │   ├── FeaturedAppCard.tsx / ModelCard.tsx
│   │   └── ui/                # shadcn/ui primitives (40+ components)
│   ├── hooks/                 # use-mobile, use-toast
│   └── lib/utils.ts           # cn() class merger
├── vite.config.ts             # Vite + @vitejs/plugin-react-swc, `@` alias
├── tailwind.config.ts
├── tsconfig*.json
└── package.json
```

## Prerequisites

- **Node.js** ≥ 18 and **npm** ≥ 9

No API keys or environment variables are needed — everything is bundled.

## Getting Started

```bash
git clone https://github.com/girishlade111/leonardo-AI-ideogram-ai-AI-Agent-.git
cd leonardo-AI-ideogram-ai-AI-Agent-
npm install        # or: npm ci  (uses package-lock.json exactly)
npm run dev        # dev server with hot reload
```

The app opens at the Vite dev URL printed in the terminal (default `http://localhost:8080` per `vite.config.ts`).

## Available Scripts

| Command           | Description |
|-------------------|-------------|
| `npm run dev`     | Start the Vite dev server with hot reload. |
| `npm run build`   | Production build into `dist/` (minified, hashed filenames). |
| `npm run build:dev` | Build in development mode. |
| `npm run preview` | Preview the production build locally. |
| `npm run lint`    | Run ESLint over the project. |

## Deployment

The production build is a fully static bundle (`dist/`), so any static host works:

```bash
npm run build      # outputs ./dist
```

- **GitHub Pages (automated)** — this repo ships a `.github/workflows/deploy-pages.yml` workflow: every push to `main` runs `npm ci` + `npm run build` and deploys `dist/` via GitHub Pages. `vite.config.ts` sets `base: "./"` so assets resolve under the project subpath, and `dist/index.html` is copied to `dist/404.html` so client-side routes survive refreshes.
- **Vercel / Netlify** — import the repo, framework preset **Vite**, build command `npm run build`, output directory `dist`.
- **Any static host** — upload the contents of `dist/`.

## Notes

- `index.html` loads `https://cdn.gpteng.co/gptengineer.js` (Lovable's runtime tagger) — harmless, can be removed for a fully self-contained build.
- `src/pages/Index.tsx` contains a `useEffect` that `fetch`es `/logo.svg` and logs when it is missing — dev-only diagnostic, safe to remove.

## License

UI concept / educational demo generated with Lovable. Artwork bundled under `public/lovable-uploads/` was AI-generated for this concept.

---

**Built by Girish Lade** — [ladestack.in](https://ladestack.in)
