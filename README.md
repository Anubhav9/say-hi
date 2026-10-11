# Portfolio v2 — Astro (no CMS, no TypeScript)

A lightweight, single-page portfolio inspired by the supplied mockup.

## Run locally

Install Node.js 20.3+ (Node 22 LTS recommended), then:

```bash
npm install
npm run dev
```

Open the local URL printed by Astro (usually http://localhost:4321).

## Production build

```bash
npm run build
npm run preview
```

The static website is generated in `dist/`. No production Node server, database, CMS, or TypeScript is needed.

## Updating content

Edit these files:

- `src/data/profile.json` — intro, location, social links, email, Medium URL
- `src/data/projects.json` — projects, links, tags, images
- `src/data/talks.json` — conferences, actual talk titles, photographs, slides, recordings
- `src/data/articles.json` — Medium article metadata and links
- `src/data/experience.json` — career history

Each talk/project/article supports `featured: true` to appear initially. Set `featured: false` for entries that appear under the expandable section. Add as many entries as you like. The project and article expansion control appears only when there are non-featured entries.

### Images

Put images in `public/images/` and reference them as `/images/filename.jpg` in JSON. The starter includes illustrative SVG artwork; replace with your own authorized images. Talk cards intentionally show PHOTO COMING SOON until you provide photos.

### Medium

Paste your Medium profile URL into `profile.json` and actual article URLs into `articles.json`. This version uses manually curated entries; it does not automatically fetch Medium or rely on its RSS uptime. You can later add a build-time RSS sync without changing the article component.

### Deployment

- **Cloudflare Pages / Netlify**: build command `npm run build`, output directory `dist`.
- **GitHub Pages**: works with a custom domain or root site. For a repository subpath (`username.github.io/repo/`), configure Astro `site` and `base` and ensure public asset URLs use the base path.

## Notes

- Blank URLs are deliberately hidden from the UI.
- Replace placeholder talk titles and Medium articles before publishing.
- Components are under `src/components/`, styles in `src/styles/global.css`.
- Astro `.astro` files use ordinary JavaScript in frontmatter; there are no `.ts` or `.tsx` files.
