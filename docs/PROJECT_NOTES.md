# Project notes (bauerperception-site)

These notes summarize what’s in this repository today (based on the current code), how to edit content, and how the site is structured.

## What this is

- **Framework**: [Astro](https://astro.build/) (static site)
- **Goal**: a fast, simple professional landing page for `bauerperception.com`
- **Hosting target**: Cloudflare Pages (build output: `dist`)

## Key structure

- **Primary pages**
  - `src/pages/index.astro`: home page (renders most sections)
  - `src/pages/blog/index.astro`: blog placeholder/stub page
- **Layout**
  - `src/layouts/BaseLayout.astro`: global HTML shell + global styles + navigation + footer
- **Content source**
  - `src/site-data.json`: primary content (name, title, positioning, highlights, experience, skills, etc.)
- **Config**
  - `astro.config.mjs`: sets canonical `site` URL (`https://bauerperception.com`)

## Editing content (common tasks)

### Update name/title/positioning/contact links

Edit `src/site-data.json`:

- `name`, `title`, `location`, `email`
- `links.LinkedIn`, `links.GitHub`
- `positioning` (the main “headline” paragraph)

### Update experience / bullets

Edit `src/site-data.json`:

- `experience[]`: each entry has `company`, `role`, `location`, `dates`, `summary`, and `bullets[]`

### Update skills / stack tags

Edit `src/site-data.json`:

- `coreDomains[]`: each has a `label` and `items[]` list (displayed as “tags”)

### Update navigation / sections

Edit `src/layouts/BaseLayout.astro` (nav links) and/or `src/pages/index.astro` (sections/IDs):

- Current section anchors: `#strengths`, `#experience`, `#skills`, `#credentials`, `#contact`
- Blog link goes to `/blog` (currently a stub)

## Styling

- Styling is currently **inline global CSS** in `src/layouts/BaseLayout.astro` via `<style is:global>`.
- The design uses a small CSS variable palette (`--bg`, `--header`, `--element`, etc.) and “card” components built with simple utility-ish classes.
- Palette source: [Color Hunt palette](https://colorhunt.co/palette/ebf4dd90ab8b5a78633b4953)

## Blog status

- `/blog` exists as a **stub** (`src/pages/blog/index.astro`) so content can be added later without redesigning navigation.
- There is no collection/content pipeline in this repo yet (no `src/content/` usage).

## Deployment notes (Cloudflare Pages)

- **Framework preset**: Astro
- **Build command**: `npm run build`
- **Output directory**: `dist`
- **Node**: 18+ (20 is fine)


