# a-lang.github.io

A-Lang's personal website — a resume-style single-page site with terminal dashboard aesthetics.

## Features

- **Dark / Light theme** toggle with `localStorage` persistence
- **Bilingual (zh/en)** with runtime language switching via `data-i18n` attributes
- **Terminal dashboard** visual design (monospace accents, scanline effects, glowing borders)
- **Hover image preview** — large preview overlay appears when hovering over project thumbnails
- **Responsive layout** — adapts from mobile to desktop
- **Zero dependencies** — no build tools, no frameworks, no package manager

## Built With

This site was handcrafted using [OpenCode](https://opencode.ai) with two AI-assisted skills:

- **[Superpowers](https://github.com/obra/superpowers)** — structured workflows for planning, debugging, and code review
- **[Web Design Engineer](https://github.com/ConardLi/garden-skills/)** — production-grade frontend design with anti-generic-AI aesthetics

## Local Development

```bash
python3 -m http.server 8080
# → http://localhost:8080
```

No build step required.

## Project Structure

```
index.html          # The entire site (~1800 lines)
assets/             # Static assets (fonts, images, screenshots)
```

## License

MIT