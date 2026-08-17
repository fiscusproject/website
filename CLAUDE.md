# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Source of [fiscusproject.eu](https://fiscusproject.eu) — the website of Fiscus, a free and open-source, self-hosted fiscalization service for Europe. A Hugo static site using the [Hextra](https://github.com/imfing/hextra) theme.

## Commands

Toolchain (Hugo extended + Go) is pinned in `mise.toml` and installed via [mise](https://mise.jdx.dev):

```sh
mise install        # one-time setup
hugo server         # dev server at http://localhost:1313
hugo --minify       # production build into public/ (what CI runs)
```

There are no tests or linters. `public/` is generated build output and gitignored — never edit it by hand.

## Architecture

- **Theme via Hugo module**: Hextra is imported in `hugo.toml` / `go.mod`, not vendored. There is no `themes/` directory; to customize the theme, override files in `layouts/` or `assets/` (e.g. `assets/css/custom.css` is Hextra's designated custom-CSS hook).
- **Content**: `content/_index.md` is currently the entire site — a single landing page built from Hextra shortcodes (`hextra/hero-*`, `hextra/feature-card`). Site config lives in `hugo.toml`.
- **Branding**: brand colors in `assets/css/custom.css` follow the separate `brandbook` repo, which is canonical (navy `#1a2846` on light backgrounds, amber/gold `#c38f24` on dark). Logos and social images live in `static/images/`.
- **Hand-authored static files**: `static/robots.txt` and `static/llms.txt` are maintained by hand (`enableRobotsTXT = false` in config). Search is disabled until docs pages exist.

## Deployment

Every push to `master` triggers `.github/workflows/deploy.yml`: mise installs the pinned toolchain, `hugo --minify` builds, then the output syncs to S3 (`--delete`) and CloudFront is invalidated. AWS infrastructure is managed separately in the `website-infrastructure` repo. A second workflow mirrors the repo to Codeberg.

## Licensing

Code (templates, config, tooling) is MIT; site content in `content/` is CC BY-SA 4.0 (`LICENSE-content`). The Fiscus name and logo are covered by neither — they fall under the brandbook repo's trademark policy. Keep this split in mind when adding files.
