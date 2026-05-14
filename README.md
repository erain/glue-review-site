# glue-review-site

Marketing homepage for [`glue-review`](https://github.com/erain/glue/tree/main/agents/glue-review), the AI code-review agent for AI coding agents.

Astro + Tailwind, statically generated, deployed via Vercel.

## Dev

Requires Node 22+.

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # static output → ./dist/
npm run preview  # serve ./dist/ locally
```

## Layout

```
src/
  layouts/Base.astro       page shell (head, header, footer)
  components/Section.astro numbered-section block, like skillfully.sh
  pages/index.astro        the single page — 7 sections + FAQ
  styles/global.css        Tailwind v4 + theme tokens
public/favicon.svg         purple action-branded mark
```

The site is **one page on purpose** — install snippet in §03 is the
primary CTA. The numbered section rhythm (01 / 02 / …) is the
narrative spine.

## Content edits

All copy lives in [`src/pages/index.astro`](src/pages/index.astro)
above the markup. The install snippet, the example PR comment, and
the fork-snippet are hoisted into JS template strings at the top of
the frontmatter so the markup stays scannable.

## Deploy

Vercel auto-detects Astro. To wire it up the first time:

1. Vercel dashboard → Add New → Project → Import `erain/glue-review-site`.
2. Framework preset: Astro (auto-detected).
3. Root directory: `./`.
4. Build command: `npm run build`. Output directory: `dist/`.
5. Deploy.

Every push to `main` auto-deploys. PRs get preview URLs.
