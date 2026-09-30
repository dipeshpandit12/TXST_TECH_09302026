# Confiance

Marketing site for **Confiance**, which helps businesses show up correctly in AI assistant answers.

Built with React, TypeScript, Vite and [Motion](https://motion.dev).

## Run it

Requires Node 20 or newer.

```bash
npm install
npm run dev       # local dev server
npm run build     # type-check and build to dist/
npm run preview   # serve the production build
npm run lint      # lint with oxlint
```

## Pages

| Route      | Contents                                                          |
| ---------- | ----------------------------------------------------------------- |
| `/`        | Animated hero, "How Confiance works" dashboard tour, product video |
| `/product` | How it works, plus the Trust section                              |
| `/pricing` | Local, Growth and Enterprise plans, with full and minor loop details |

## Settings

Optional. Put them in `.env.local`:

| Variable             | Default      | What it does                                             |
| -------------------- | ------------ | -------------------------------------------------------- |
| `VITE_DASHBOARD_URL` | `/dashboard` | Where the "Open dashboard" buttons go (separate project) |
| `VITE_YOUTUBE_URL`   | empty        | Product video on Home; empty shows "coming soon"         |
| `VITE_HERO_IMAGE`    | empty        | Hero background image; empty uses the animated scene     |

## Themes

- **Night** (default): a dark starry sky with a rocket.
- **Sunny**: a warm sunrise with a golden page.

The toggle in the nav switches between them, and the site remembers each visitor's choice. Colors live as tokens at the top of `src/index.css`. All animation respects the system "reduce motion" setting.

## Project structure

```
public/        dashboard.png, logo-mark.png
src/
  pages/       Home, Product, Pricing
  sections/    HomeHero, HowItWorks, Trust, Video
  components/  Chrome (nav), HeroScene, CursorDot, Effects, Icons
  App.tsx      routes
  config.ts    dashboard link, video link, hero image
  theme.ts     night / sunny theme
  motion.ts    shared animation helpers
  index.css    styles and color tokens
```

## Deploy

`npm run build` produces a static site in `dist/`. Configure your host to serve `index.html` for unknown paths (client-side routing), and either redirect `/dashboard` to the dashboard app or set `VITE_DASHBOARD_URL`.
