# CLAUDE.md

Photo diary site (diary.kkhys.me). Astro 6 static site on Cloudflare Pages. TypeScript strictest mode. Vanilla CSS (kiso.css reset + uchu.css OKLCH palette). Path alias: `#/*` → `./src/*`.

## Project Map

- `src/pages/` — Astro pages
- `src/layouts/` — Layout components
- `src/styles/` — Global CSS with light-dark() theme switching
- `public/` — Static assets (images, robots.txt)

## How to Work

- Dev tools managed by Nix Flake (`flake.nix`). Run `direnv allow` to autoload.
- All commands: see `scripts` in `package.json`
- CI: lint → type check → build. Add `skip-ci` label to PRs to skip.

## Gotchas

- `exactOptionalPropertyTypes: true` — optional props need `| undefined`, not just `?:`
- `.astro` files can't be imported from `.ts` (tsc doesn't resolve them)
