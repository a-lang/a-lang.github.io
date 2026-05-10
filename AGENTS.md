# Personal Site — AGENTS.md

## Project Overview

A-Lang's resume-style personal website. Single static HTML file with terminal dashboard aesthetics, dark/light theme toggle, and bilingual (zh/en) support. No build tools, no frameworks, no package manager.

## Architecture

- **`index.html`** — The entire site (HTML + CSS + JS in one file, ~1700 lines)
- **`resume/`** — Source PDF resumes (read-only reference, not served)
- **`docs/superpowers/specs/`** — Design spec
- **`docs/superpowers/plans/`** — Implementation plan

## Key Conventions

- All content data lives in JS objects inside `<script>`: `i18nData`, `featuredData`, `projectsData`, `skillsData`, `skillsTreeData`, `workData`, `certsData`
- Language switching uses `data-i18n` attributes on DOM elements + `lang.apply()` to re-render dynamic content
- Theme preference stored in `localStorage` key `a-lang-theme`; language in `a-lang-lang`
- Company names in `workData` are deliberately anonymized (industry + size format, e.g. "半導體公司（1000+ 人）") — do not use real company names
- No real name, phone, address, or photos anywhere on the site; pen name is "A-Lang"

## Design System Tokens

CSS custom properties in `:root` define the entire design system. Light theme overrides are in `.light-theme`. When modifying colors, spacing, or typography, always edit the variables first — never hardcode values in individual rules.

- Primary accent: `--color-accent` (#00e5ff dark / #007a8a light)
- Font stack: JetBrains Mono (code/headings) → Inter (body) → Noto Sans TC (Chinese)
- Spacing base: 8px

## Making Changes

- **To update project data**: Edit the JS objects at the top of `<script>` (`featuredData`, `projectsData`, etc.). Each project has `thumbnail_gradient` and `thumbnail_abbr` for placeholder thumbnails.
- **To add a project**: Add entry to `projectsData` with all required fields (`id`, `category`, `title`, `title_zh`, `title_en`, `desc_zh`, `desc_en`, `tags`, `github`, `thumbnail_abbr`, `thumbnail_gradient`). Optionally add `youtube`.
- **To add an i18n key**: Add to both `i18nData.zh` and `i18nData.en`, then add `data-i18n="key"` to the HTML element.
- **To add future real screenshots**: Replace `<div class="card-thumbnail">` with `<img src="assets/screenshots/<project-id>.png">` — create `assets/screenshots/` directory.

## Verification

```bash
# Open locally
python3 -m http.server 8080
# → http://localhost:8080
```

No lint, test, or build commands — this is a static HTML file.

## Privacy

Never add: real name, phone numbers, addresses, photos, or de-anonymized company names.