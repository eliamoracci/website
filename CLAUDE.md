# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this site is

Plain HTML + CSS academic website for Elia Moracci, hosted on GitHub Pages at `eliamoracci.github.io`. No build step, no static site generator, no dependencies. Push to `master` and it's live.

## Structure

- `index.html` — Home (bio, photo, contacts)
- `research.html` — Working papers & work in progress
- `discussions.html` — Conference discussions
- `teaching.html` — Teaching positions
- `css/style.css` — Single shared stylesheet
- `img/profile.jpg` — Profile photo
- `files/` — PDFs (CV, papers, slides)

## Deploy

```bash
git add . && git commit -m "update" && git push
```

No build command needed. GitHub Pages serves the HTML directly.

## Conventions

**Adding a paper** — copy an existing `<div class="paper">` block in `research.html` and edit it. Structure:
```html
<div class="paper">
  <h3 class="paper-title">Title</h3>
  <p class="paper-meta"><em>with Coauthor</em></p>
  <p class="paper-meta">Venue/status line</p>
  <p class="paper-links"><a href="...">Paper</a> <a href="...">Slides</a></p>
  <details class="paper-abstract">
    <summary>Abstract</summary>
    <p>...</p>
  </details>
</div>
```

**Nav bar** — duplicated across all four HTML files. When adding a new page, update `<a class="active">` in each file and add the nav link to all files.

**KaTeX** — already loaded via CDN in every page's `<head>`. Use `$...$` for inline math and `$$...$$` for display math anywhere in the HTML.

**CSS design tokens** — all colors, font, and max-width are in `:root` variables at the top of `css/style.css`. Change them there, not inline.

**PDFs** — place in `files/`. Paper links currently point to `https://eliamoracci.github.io/website/papers/` (a separate repo); update hrefs as needed.

**Active nav link** — each page sets `class="active"` on its own nav link. This adds a bold underline via CSS.
