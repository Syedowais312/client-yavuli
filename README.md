# Yavuli — Student Marketplace (Frontend)

A lightweight, production-ready React + Vite frontend for a student marketplace demo. Built with TypeScript, Tailwind CSS and a set of shadcn-style UI primitives. Includes example data and a Supabase integration for auth / data if you want to connect a backend.

## Key features
- SPA with multiple pages (Explore, Product Details, Sell, Profile, Cart, Auth)
- Reusable UI primitives under `src/components/ui` (accordion, dialog, input, toast, etc.)
- Product listing UI: `ProductCard`, `FilterSidebar`, `Navbar`
- Demo data: `src/data/dummyListings.json`
- Supabase client in `src/integrations/supabase` (optional backend)
- Tailwind CSS + PostCSS + Vite for fast dev and optimized builds
- TypeScript and ESLint configuration included

## Quick start (Windows)
1. Install dependencies
```bash
npm install
```

2. Create a `.env` at project root (examples below). For local dev with Supabase, add:
```env
VITE_SUPABASE_URL=your-supabase-url
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
```

3. Run the dev server
```bash
npm run dev
```

4. Build for production
```bash
npm run build
npm run preview
```

(If you use PowerShell, run the same npm commands there.)

## Recommended scripts
- npm run dev — run Vite dev server  
- npm run build — build production assets  
- npm run preview — locally preview the production build  
- npm run lint — lint project (if configured)  
- npm run type-check — run TypeScript checks (if configured)

Check `package.json` for the exact script names available in this repo.

## Project structure (important files)
- src/
  - main.tsx — app bootstrap and router
  - App.tsx — app shell and route layout
  - pages/ — route pages (Explore, ProductDetails, Sell, Profile, Cart, Login, Signup, etc.)
  - components/
    - Navbar.tsx, ProductCard.tsx, FilterSidebar.tsx
    - ui/ — small UI primitives and wrappers (dialog, button, input, toast, chart, etc.)
  - data/dummyListings.json — sample product data
  - integrations/supabase/
    - client.ts — Supabase client wrapper
    - types.ts — Supabase-related types
- public/ — static assets (robots.txt, etc.)
- tailwind.config.ts, postcss.config.js — Tailwind + PostCSS config
- tsconfig.json — TypeScript config
- eslint.config.js — linting rules

## Supabase integration notes
- The project expects Vite-style env variables (VITE_SUPABASE_URL, VITE_SUPABASE_ANON_KEY). Confirm names in `src/integrations/supabase/client.ts` and set them in `.env`.
- If you don't connect Supabase, the app falls back to demo JSON for listings in many places.

## How to extend
- Add pages under `src/pages` and route them in `App.tsx`.
- Add shared components under `src/components` or primitives under `src/components/ui`.
- Replace `src/data/dummyListings.json` with API calls or wire the Supabase client for real data.

## Testing & type checks
- Add tests and a test runner (Vitest/Jest) as needed.
- Run TypeScript checks with `npm run type-check` (if configured).

## Common troubleshooting
- Styles not loading: ensure Tailwind is configured in `index.css` and `tailwind.config.ts`. Restart the dev server after installing Tailwind.
- Env vars not picked up: Vite requires `VITE_` prefix for client-side env variables and a dev-server restart after changes.
- Broken imports: check path aliases if present; `components.json` may define aliases used by the project.

## Contributing
- Follow existing coding style and components pattern in `src/components/ui`.
- Run linter and type checks before opening PR.
- Add Storybook or component docs if you add many UI primitives.
