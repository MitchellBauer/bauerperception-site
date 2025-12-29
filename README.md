# bauerperception-site

Source repository for bauerperception.com.

This site serves as a professional landing page highlighting
IT leadership experience, systems architecture, and selected projects.

Built as a simple, fast, static site.
Not intended as a blog or application repository.

Live site: https://bauerperception.com
LinkedIn: https://linkedin.com/in/mitchelljbauer

# bauerperception.com (Astro + Cloudflare Pages)

## Local dev
```bash
npm install
npm run dev
```

## Build
```bash
npm run build
npm run preview
```

## Deploy to Cloudflare Pages
- Framework preset: **Astro**
- Build command: `npm run build`
- Build output directory: `dist`
- Node version: 18+ (20 is fine)

## Notes
- Main page: `src/pages/index.astro`
- Blog stub: `src/pages/blog/index.astro`
- Edit content in `src/site-data.json`
